<template>
    <div v-show="country === 'Bangladesh'">
        Bangladesh
    </div>
    <div v-show="country === 'uk'">
        another country
    </div>
    <ul>
        <li v-for="item in items" :key="item">{{item.message}}</li>
    </ul>
    <ul>
        <li href="#" v-for="(winterFood, index) in winterFoods" v-bind:key="winterFood">
            <a href="">{{country}}-{{index}}-{{winterFood}}</a>
        </li>
    </ul>
    <div v-for="(value , name , index) in book" v-bind="books" :key="value">
        {{index}} : {{name}} : {{value}}
    </div>
    <div v-for="n in 10" v-bind:key="n">
        {{n}}
    </div>
    <div>
       result is : {{resultNum}}
    </div>
    <button @click="addNumber">addnumber</button>

    <div v-once>
        old city name: {{city}}
    </div>
    <div>
        updated city name: {{city}}
        <!-- {{update()}} -->
    </div>
    <button v-on:click="update()">update city</button>
    <ul>
        <li v-for="rolls in roll" v-bind:key="rolls">
            <a href="">{{rolls}}</a>
        </li>
    </ul>
    <button v-on:click="rollArray">roll array</button>
    <button v-on:click="counter">counter</button>
    <p>counter : {{count}}</p>
    <button v-on:click="decrement">decrement</button>
    <button v-on:click="myalert">alert</button>
</template>
<script>
    export default{
        data(){
            return{
                country: 'uk',
                items: [
                    {message: 'foo'},
                    {message: 'fii'}
                ],
                winterFoods: ['coffi','shak','mula'],
                count: 0,
                book: {
                    title: 'the cook book',
                    author: 'urk',
                    date: '06-12-2021'
                },
                num1: 20,
                num2: 30,
                resultNum: '',
                city: 'chittagong',
                roll: [9,2,3,4,5,6,7,8,1,10,11,11,13,12]
            }
        },
        methods: {
            addNumber: function(){
                this.resultNum =  this.num1 + this.num2;
            },
            update: function(){
                setTimeout(()=>{
                    this.city = 'chattogram';
                },3000);
            },
            rollArray: function(){
                // this.roll.push(10);
                // shift delete from start one by one
                // this.roll.shift(10);
                // pop delete from the dend one by one
                // this.roll.pop();
                // this.roll.splice(5);
                // this.roll.reverse();
                // this.roll.sort((a,b)=>a-b);
                // return this.roll.filter((a)=>{
                //     return a % 2 === 0;
                // });
                // [...new Set(this.roll)]
            },
            counter: function(){
                this.count += 1;
            },
            decrement: function(){
                this.count -= 1;
            },
            myalert: function(){
                alert('hello vue js');
            }
        }
    }
</script>
<style scoped>
    ul{
        list-style-type: none;
    }
    a{
        text-decoration: none;
    }
</style>
