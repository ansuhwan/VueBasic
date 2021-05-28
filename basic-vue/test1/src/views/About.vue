<template>
  <div>
    <v-swatches v-model="color"></v-swatches>
    <NameTest @update-name="updateName"/>
    {{name}}
  </div>
</template>

<script>
  import VSwatches from 'vue-swatches'
  import NameTest from '../components/NameTest.vue'

  // Import the styles too, globally
  import "vue-swatches/dist/vue-swatches.css"

  export default {
    components: { VSwatches,NameTest }, // window['vue-swatches'] - from CDN
    data () {
      return {
        color: '#1CA085',
        name: ""
      }
    },
    methods: {
      updateName(name) {
        this.name = name
      }
    },
  }
</script>