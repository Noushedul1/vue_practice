<template>
  <ComHome></ComHome>
  <ComProps 
    v-bind:firstname = "fstname"
    v-bind:lastname = "lname"
    v-bind:age = "myage"
    @valueupdate = "fstname = $event"
  ></ComProps>
  <form v-on:submit.prevent="formvalueupdate">
    <div>
      <label>firstname : </label>
      <input type="text" v-model="formdata.fn">
    </div>
    <div>
      <label>lastname : </label>
      <input type="text" v-model="formdata.ln">
    </div>
    <div>
      <label>password : </label>
      <input type="password" v-model.lazy="formdata.pass">
    </div>
    <div>
      <textarea 
      name="msg" 
      id="" 
      cols="30" 
      rows="10"
      v-model="formdata.message"
      >
      </textarea>
    </div>
    <div>
      <label>
      <input 
      type="checkbox"
      value="chemistry"
      v-model="check"
      >chemistry
    </label>
    <label>
      <input 
      type="checkbox"
      value="biology"
      v-model="check"
      >biology
    </label>
    </div>
    <div>
      <label>
        <input 
        type="radio"
        value="male"
        v-model="gender"
        >male
      </label>
      <label>
        <input 
        type="radio"
        value="female"
        v-model="gender"
        >female
      </label>
    </div>
    <label>
      select
    </label>
    <select v-model="selectPriority">
      <option v-for="selects in select" v-bind:key="selects">
        {{selects}}
      </option>
    </select>
    <div>
      <input 
      type="submit" 
      value="submit"
      v-on:click.prevent="submitted">
    </div>
  </form>
  <div v-if="isSubmitted">
    <p>first name: {{formdata.fn}}</p>
    <p>last name : {{formdata.ln}}</p>
    <p>last name : {{formdata.pass}}</p>
    <p style="white-space: pre-line">message : {{formdata.message}}</p>
    <li v-for="checks in check" v-bind:key="checks">
      {{checks}}
    </li>
    <p>gender : {{gender}}</p>
    <p>cars : {{selectPriority}}</p>
  </div>
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
  <div class="client" v-on:mousemove="clientt">
    Hover me
  </div>
  <div>
    <p>clientX : {{x}}</p>
    <p>clientY : {{y}}</p>
  </div>
  <div>
    <div class="container">
      <div class="row">
        <div class="col">
          lorem
        </div>
        <div class="col">
          lorem
        </div>
        <div class="col">
          lorem <i class="bi bi-alarm"></i>
        </div>
      </div>
    </div>
  </div>
</template>
<script> 
  import ComHome from './components/Home.vue';
  import ComProps from './components/Props.vue';
  export default{
    components: {
    ComHome,
    ComProps
    },
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
        elseifCondition: 'A',
        desh: 'Bangladesh',
        friend: ['farhad','anish','joy','abdur rahman'],
        fstname: 'noushedul',
        lname: 'islam',
        myage: 25,
        x: '',
        y: '',
        formdata: {
          fn: '',
          ln: '',
          pass: '',
          message: ''
        },
        check: [],
        gender: 'male',
        selectPriority: 'bmw',
        select: ['prado','ford','bmw'],
        isSubmitted: false
      }
    },
    methods:{
      hello(){
        console.log(typeof this.bonus);
      },
      formvalueupdate: function(){
        console.log(this.formdata);
      },
      clientt: function(event){
        this.x = event.clientX;
        this.y = event.clientY;
      },
      submitted: function(){
        this.isSubmitted = true;
      }
    },
    computed: {
      
    }
  }
</script>
<style scoped>
  .client{
    height: 100px;
    width: 100px;
    background: red;
    color: white;
  }
</style>
