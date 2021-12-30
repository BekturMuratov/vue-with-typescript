<template>
    <div class="job-list">
        <p>Order by {{order}}</p>
        <ul>
            <li v-for="job in orderedJobs" :key="job.id">
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
import { computed, defineComponent, PropType } from 'vue';
import Job from '@/types/job';
import OrderTerm from '@/types/orderTerm';
export default defineComponent({
   props:{
       jobs: {
           required: true,
           type: Array as PropType<Job[]>
       },
       order:{
           required: true,
           type: String as PropType<OrderTerm>
       }
   },
   setup(props){
       const orderedJobs = computed(() => {
           return [...props.jobs].sort((a:Job, b:Job) => {
               return a[props.order] > b[props.order] ? 1 : -1
           })
       })

       return {orderedJobs}
   }
})
</script>

<style scoped>
 .job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 0;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>