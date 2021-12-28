<template>
<div class="app">
 <p>{{name}} - {{age}}</p>
 <button @click="changeName('Chuck')">change name</button>
 <button @click="changeAge('18')">change age</button>
</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';


export default defineComponent({
  name: 'App',
  components: {},
  data(){
    return {
      name: 'Link',
      age: 25 as string | number,
    }
  },
  methods:{
    changeName(name:string){
      this.name = name
      return name
    },
    changeAge(age: number | string){
      this.age = age
      return age
    }
  }
});
</script>

<style>

</style>
