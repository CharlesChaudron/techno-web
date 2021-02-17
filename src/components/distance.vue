<template>
    <div>
        <input type="number" v-model="km">
        <input type="number" v-model="m">
        <input type="number" v-model="cm">
        <input type="number" v-model="mm">
    </div>
</template>

<script lang="ts">
import { ref, defineComponent, computed } from 'vue'

export default defineComponent({
    name: 'distance',
    data() {
        return {
            km:0,
            m:0,
            cm:0,
            mm:0,
        }
    },
    watch: {
        km: function (val) {
            this.m = val*1000
        },
        m: function (val) {
            this.km = val/1000
            this.cm = val*100
        },
        cm: function (val) {
            this.m = val/100
            this.mm = val/10
        },
        mm: function (val) {
            this.km = val/1000/1000
        }
    }

})
</script>