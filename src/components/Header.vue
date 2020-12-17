<template>
  <section class="jumbotron">
      <h3 class="jumbotron-heading">Search Github Users</h3>
      <div>
        <input type="text" placeholder="enter the name you search" v-model="keyword"/>
        <button @click="btn">Search</button>
      </div>
    </section>
</template>

<script>
export default {
  name: '',
  data() {
      return {
          keyword:''
      }
  },
  methods:{
      btn(){
          let keyword=this.keyword
         if(keyword.trim()){
              this.$bus.$emit('Search',keyword)
         }else{
             alert('关键字格式不合法')
         }

         this.keyword=''
      }
  }
}
</script>

<style scoped>

</style>
