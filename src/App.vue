<template>
<div class="app">
<JobList :jobs="jobs"/>
</div>
</template>

<script lang="ts">
import { defineComponent, ref,  } from 'vue';
import Job  from './types/job';
import  JobList from './components/JobList.vue';


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
    return {jobs}
  },

});
</script>

<style>

</style>
