<template>
  <div>
    <h1>{{name}}</h1>
    <input @input="checkValue" type="number" v-model="fvalue" maxlength="3" />

    <input @input="checkValue" type="number" v-model="svalue" maxlength="3"/>

    <input @input="checkValue" type="number" v-model="tvalue" maxlength="3" />

    <button @click.prevent="updataValue" >색상 알아보기</button>

    <div class="upper" v-if="clickBtn">색상은 {{result}}</div>
    <v-swatches v-if="clickBtn" v-model="result" :trigger-style="{width: '100px', height: '100px'}"></v-swatches>
    
  </div>
</template>


<script>
  import VSwatches from 'vue-swatches'

  // Import the styles too, globally
  import "vue-swatches/dist/vue-swatches.css"

export default {
  components: { VSwatches },
  data() {
    return {
      name: 'MILK',
      fvalue: "",
      svalue: "",
      tvalue: "",
      result: "",
      clickBtn: false,

    }
  },
  methods: {
    updataValue() {
      const aa = parseInt(this.fvalue).toString(16);
      const bb = parseInt(this.svalue).toString(16);
      const cc = parseInt(this.tvalue).toString(16);

      this.result ='#' + aa + bb+ cc
      this.clickBtn = true
    },
    checkValue(){
      if(parseInt(this.fvalue) > 255){
        this.fvalue = 255
      }
      if(parseInt(this.svalue) > 255){
        this.svalue = 255
      }
      if(parseInt(this.tvalue) > 255){
        this.tvalue = 255
      }
    }
  },
}
</script>

<style scoped>
div{
  display: flex;
  flex-direction: column;
  max-width: 500px;
  margin: 0 auto;
}
  h1 {
    color: steelblue;
  }
  .upper{
    text-transform: uppercase;
  }
</style>