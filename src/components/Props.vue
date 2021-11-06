<template>
    <div>
        {{firstname}}
        {{lastname}}
        {{age}}
        <button v-on:click="updatevalue()">custom methods</button>
    </div>
    
</template>
<script>
    export default{
       props: {
           firstname: String,
           lastname: String,
           age: Number
       },
       methods: {
           updatevalue: function(){
               this.$emit('valueupdate','mohammod');
           }
       }
    }
</script>
<style scoped>

</style>
