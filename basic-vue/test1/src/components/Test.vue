<template>
  <div>
      <p>{{name}}</p>
      <button @click.prevent="updateName">{{reName ? "되돌리기" : "색상 알아보기"}}</button>
  </div>
</template>


<script>
export default {
  data() {
    return {
      name: 'aaaaa',
      reName: false,
    }
  },
  methods: {
    updateName() {
      if(this.reName === false){
        this.name = '안수환'
        this.reName = true
      }else{
        this.name = 'aaaa'
        this.reName = false
      }

      
    }
  },
}
</script>


<style scoped>

</style>