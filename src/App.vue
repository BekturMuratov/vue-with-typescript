<template>
<div class="app">
  <header>
    <div class="irder">
  <button @click="handleClick('title')">order by title</button>
  <button @click="handleClick('salary')">order by salary</button>
  <button @click="handleClick('company')">order by company</button>
    </div>
  </header>

<JobList :jobs="jobs" :order="order" />
</div>
</template>

<script lang="ts">
import { defineComponent, ref,  } from 'vue';
import Job  from './types/job';
import  JobList from './components/JobList.vue';
import  OrderTerm from './types/orderTerm';

export default defineComponent({
  name: 'App',
  components: {JobList},
  setup(){
    const jobs = ref<Job[]>([
      {title:'frontend developer', company:'maddevs',salary:70000, id:'1'},
      {title:'backend developer', company:'sun finance',salary:120000, id:'2'},
      {title:'full stack developer', company:'growave',salary:150000, id:'3'},
      {title:'frontend developer', company:'codify',salary:60000, id:'4'},
      {title:'flutter developer', company:'oracle digital',salary:140000, id:'5'},
    ])

    const order = ref<OrderTerm>('title');

    const handleClick = (term: OrderTerm) => {
      order.value = term
    }

    return {jobs, handleClick, order}
  },

});
</script>

<style>
 header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }
</style>
