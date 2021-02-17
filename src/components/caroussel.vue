<template>
    <div>
        <button v-on:click="imagePrev">Précédente</button>
        <img v-bind:src="images[imageAffichee]" v-bind:alt="images[imageAffichee]">
        <button v-on:click="imageNext">Suivante</button>
    </div>
    
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'

export default defineComponent({
    name: 'caroussel',
    data() {
        return {
            images: [
                '../../public/images/1.jpg',
                '../../public/images/2.jpg',
                '../../public/images/3.jpg',
                '../../public/images/4.jpg',
                '../../public/images/5.jpg',
                '../../public/images/6.jpg',
            ],
            imageAffichee: 0,
        }
    },
    methods: {
        imageNext: function () {
            if (this.imageAffichee < this.images.length-1) {
                this.imageAffichee++
            } else {
                this.imageAffichee = 0
            }
        },
        imagePrev: function () {
            if (this.imageAffichee > 0) {
                this.imageAffichee--
            } else {
                this.imageAffichee = this.images.length-1
            }
        }
    }

})
</script>