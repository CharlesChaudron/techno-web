<template>
    <div>+ {{element.titre}}: {{element.contenu}}</div>
    <button v-on:click="sendDelete">Supprimer</button>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'

export default defineComponent({
    name: 'elementList',
    /*data() {
        return {
            titre: "défaut",
            contenu: "le contenu",
        }
    },*/
    emits: ['delete'],
    props: {
        element: Object,
    },
    methods: {
        sendDelete: function () {
            this.$emit('delete')
        }
    } 

})
</script>