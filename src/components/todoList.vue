<template>
    <corpsList v-bind:elements="list" @delete-by-id="delteteElement"></corpsList>
    <p>Titre</p>
    <input type="text" v-model="titreInp">
    <p>Contenu</p>
    <input type="text" v-model="contenuInp">
    <button v-on:click="save">Sauvegarder</button>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'
import corpsList from './corpsList.vue'

export default defineComponent({
    name: 'todoList',
    components: {corpsList},
    data() {
        return {
            list: [
                {titre: "première", contenu: "blablabla"},
                {titre: "deuxième", contenu: "2"},
                {titre: "troisième", contenu: "33333"},
                {titre: "quatrième", contenu: "4 en scred"},
            ],
            titreInp: "",
            contenuInp: "",
        }
    },
    methods: {
        save: function () {
            this.list.push({titre: this.titreInp , contenu: this.contenuInp})
            this.titreInp = ""
            this.contenuInp = ""
        },
        delteteElement: function(id: Number){
            this.list.splice(id, 1)
        }
    }   

})
</script>