<template>
    <input type="number" v-model="number1">
    <select v-model="operateur">
        <option v-for="operateur in operateurs" v-bind:key="operateur.caractere">{{operateur.caractere}}</option>
    </select>
    <input type="number" v-model="number2">
    <p>{{calcul}}</p>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'

export default defineComponent({
    name: 'calculatrice',
    data() {
        return {
            operateurs: [
                {caractere: '*'}, 
                {caractere: '/'}, 
                {caractere: '+'}, 
                {caractere: '-'},
            ],
            number1: 0,
            number2: 0,
            operateur: '+',
            result: 0,
        }
    },
    computed: {
        calcul(){

            if (this.operateur=='+')
                return Number(this.number1) + Number(this.number2)
            if (this.operateur=='-')
                return this.number1 - this.number2
            if (this.operateur=='*')
                return this.number1 * this.number2
            if (this.operateur=='/')
                return this.number1 / this.number2
        }
    }    

})
</script>