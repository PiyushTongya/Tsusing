<template>
  <div class="app">
    <header>
      <div class="order">
      
    <button @click="handleClick('title')">order by title</button>
    <button @click="handleClick('salary')">order by salary</button>
    <button @click="handleClick('location')">order by location</button>
   
      </div>
    </header>
    <jobsList :jobs="jobs" :order="order"/>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import JobsList from './components/JobsList.vue';
import Job from './components/types/job';
import OrderTerm from './components/types/OrderTerm';


export default defineComponent({
  name: 'App',
  components: {JobsList},
  setup() {
    const jobs = ref<Job[]>([
      { title: "farm worker", location: "Jaipur", salary: 2345, id: "1" },
      { title: "worker", location: "Rajasthan", salary: 20000, id: "2" },
      { title: "fam", location: "Chittorgarh", salary: 20345, id: "3" },
      { title: "horn", location: "Bhilwara", salary: 4555, id: "4" },
      { title: "Hosted", location: "Delhi", salary: 3444, id: "5" },
      { title: "Vue", location: "landon", salary: 45000, id: "6" },
      { title: "react", location: "hydrabad", salary: 6444, id: "7" }
    ]);
      const order = ref<OrderTerm>('title')
    const handleClick=(term:OrderTerm)=>{
      order.value = term
    }

    return {
      jobs,handleClick,order
    };
  }
});
</script>

<style>
header{
  text-align: center;
}
header .order{
  margin-top: 20px;
}
button{
  margin:  0 20px;
  color: #1195c9;
   border:3px solid #1195c9;
   background: #d5f0ff;
   padding: 8px 16px;
   cursor: pointer;
   font-weight: bold;
}
</style>
