<template>
    <h2 class="text-center ml-6 font-bold text-2xl py-4 text-purple-800">
      Order by {{ order }}
    </h2>
    <transition-group name="list" class="flex items-center flex-col " tag="ul">
      <li
        v-for="job in orderJob" :key="job.id"
        class="py-3 px-6 my-2 mx-4 bg-white text-black md:w-[70%] list-none"
      >
        <h2 class="text-lg font-medium">
          {{ job.name }}
        </h2>
        <p>Salary : {{ formatToCurrency(job.salary) }}</p>
        <p>Location : {{ job.location }}</p>
        <p class=" pt-2 text-[14px]">
          {{ job.description }}
        </p>
      </li>
    </transition-group>
</template>
<script setup lang="ts">
import { defineProps, PropType, computed } from 'vue';
import Job from '../types/Job';
import OrderTerm from '../types/OrderTerm';

const props = defineProps({
  jobs: {
    required: true,
    type: Array as PropType<Job[]>
  },
  order: {
    required: true,
    type: String as PropType<OrderTerm>
  }
});
const formatToCurrency = (amount: number) => {
  return "Rp. " + amount.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$&,");
};
const orderJob = computed(() => {
  return [...props.jobs].sort((a: Job, b: Job) => {
    return a[props.order] > b[props.order] ? 1 : -1
  })
})

console.log(props.jobs);
</script>

<style>
.list-move{
  transition: all 0.5s;
}
</style>