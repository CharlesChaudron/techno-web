<template>
  <calculatrice></calculatrice>
  <hr>
  <distance></distance>

</template>

<script lang="ts">
import { defineComponent } from 'vue'
import calculatrice from './components/calculatrice.vue'
import distance from './components/distance.vue'

export default defineComponent({
  name: 'App',
  components: { calculatrice, distance },
})

</script>