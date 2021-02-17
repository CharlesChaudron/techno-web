<template>
    <elementList v-for="element in elements" v-bind:key="element" v-bind:element="element" @delete="deleteById(elements.indexOf(element))"></elementList>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'
import elementList from './elementList.vue'

export default defineComponent({
    name: 'corpsList',
    components: {elementList},
    data() {
        return {
            
        }
    },
    emits: ['delete-by-id'],
    props: {
        elements: Array,
    },
    methods: {
        deleteById: function (id: Number) {
            this.$emit('delete-by-id', id)
        }
    }

})
</script>