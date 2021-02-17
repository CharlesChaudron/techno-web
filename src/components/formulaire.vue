<template>
    <div v-show="formShow">
        <p>Nom</p>
        <input type="text" v-model="nom">
        <p>Prénom</p>
        <input type="text" v-model="prenom">
        <p>Date de naissance</p>
        <input type="date" v-model="date">
        <p>mail</p>
        <input type="mail" v-model="mail">
        <button type="submit" v-on:click="hide">Valider</button>
    </div>
    <p v-show="formShow == false">Félicitations, vous êtes inscrit</p>
</template>

<script lang="ts">
import { ref, defineComponent, computed } from 'vue'

export default defineComponent({
    name: 'formlaire',
    data() {
        return {
            nom: "",
            prenom: "",
            date: "",
            mail: "",
            formShow: true,
        }
    },
    methods: {
        hide: function () {
            this.formShow = false
        },
    }
})
</script>