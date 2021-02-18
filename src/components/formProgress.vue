<template>
    <p v-show="show>=0">Etape 1</p>
    <p v-show="show>=1">Etape 2</p>
    <p v-show="show>=2">Etape 3</p>
    <div v-show="show==show0">
        <p>Données personnelles</p>
        <input type="text">
        <input type="text">
        <input type="number">
        <select name="" id="">
            <option value="m"></option>
            <option value="f"></option>
        </select>
    </div>
    <div v-show="show==show1">
        <p>Adresse</p>
        <input type="text">
        <input type="text">
    </div>
    <div v-show="show==show2">
        <p>Conditions générales</p>
        <input type="checkbox">
    </div>
    <button v-on:click="next" v-show="show!=show2">Etape suivante</button>
</template>

<script lang="ts">
import { ref, defineComponent, computed } from 'vue'

export default defineComponent({
    name: 'formProgress',
    data() {
        return {
            show0: 0,
            show1: 1,
            show2: 2,
            show: 0,
        }
    },
    methods: {
        next: function () {
            if (this.show < 2)
                this.show++
        }
    }
})
</script>