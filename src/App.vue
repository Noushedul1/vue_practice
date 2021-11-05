<template>
  <ComHome></ComHome>
  <p>{{fname}}</p>
  <p><a :href=google target="_blank">vue</a></p>
  <div v-html="code"></div>
  <p v-text="msg"></p>
  <img :src=photo alt="">
  <ul>
    <li v-for="range in rollrange" :key="range">
      <a href="">{{range}}</a>
    </li>
  </ul>
  <button @click="hello">click</button>
  <div v-if="ifElsecondition">
    if is true 
  </div>
  <div v-else>
    if is false
  </div>
  <div v-if="elseifCondition === 'D' ">
    A
  </div>
  <div v-else-if="elseifCondition === 'B' ">
    B
  </div>
  <div v-else-if="elseifCondition === 'C' ">
    C
  </div>
  <div v-else>
    no Alphabet
  </div>
</template>
<script> 
  import ComHome from './components/Home.vue';
  export default{
    components: {ComHome},
    data(){
      return{
        fname: 'noudshed',
        sallary: 2000,
        bonus: 1000,
        google: 'https://v3.vuejs.org/guide/installation.html#release-notes',
        code: '<h1>hello noushed</h1>',
        msg: 'southern university of bangladesh',
        photo: 'https://source.unsplash.com/random/201x200?computer',
        rollrange: [1,2,4,5,6],
        ifElsecondition: true,
        elseifCondition: 'A'
      }
    },
    methods:{
      hello(){
        console.log(typeof this.bonus);
      }
    }
  }
</script>
<style scoped>
  
</style>
