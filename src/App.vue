<template>
  <calculatrice></calculatrice>
  <hr>
  <distance></distance>
  <hr>
  <formulaire></formulaire>
  <hr>
  <caroussel></caroussel>
  <hr>
  <todoList></todoList>
  <hr>
  <formProgress></formProgress>
  <hr>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import calculatrice from './components/calculatrice.vue'
import distance from './components/distance.vue'
import formulaire from './components/formulaire.vue'
import caroussel from './components/caroussel.vue'
import todoList from './components/todoList.vue'
import elementList from './components/elementList.vue'
import formProgress from './components/formProgress.vue'

export default defineComponent({
  name: 'App',
  components: { calculatrice, distance, formulaire, caroussel, todoList, elementList, formProgress },
})

</script>