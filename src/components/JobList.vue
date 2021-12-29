<template>
    <div class="job-list">
        <ul>
            <li v-for="job in jobs" :key="job.id">
                <h2>{{job.title}} in {{job.company}}</h2>
                <div class="salary">
                  <p> {{job.salary}} $</p> 
                </div>
                <div class="description">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid, quisquam dolor eaque maiores assumenda alias possimus nisi officiis ex fugiat optio illo omnis quam illum neque maxime. Aut, nemo blanditiis?</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Job from '@/types/job';

export default defineComponent({
   props:{
       jobs: {
           required: true,
           type: Array as PropType<Job[]>
       }
   }
})
</script>

<style scoped>

</style>