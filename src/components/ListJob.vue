<template>
		<ul class="my-10 py-10">
			<li
				v-for="job in jobs" :key="job.id"
				class="py-3 px-6 my-2 mx-4 bg-white text-black"
			>
				<h2 class="text-lg font-medium">
					{{ job.name }}
				</h2>
				<p>Salary : {{ formatToCurrency(job.salary) }}</p>
        <p>Location : {{ job.location }}</p>
			</li>
		</ul>
</template>
<script setup lang="ts">
import { defineProps, PropType } from 'vue';
import Job from '../types/Job';

defineProps({
  jobs: {
    required: true,
    type: Array as PropType<Job[]>
  },
})
const formatToCurrency = (amount: number) => {
  return "Rp. " + amount.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$&,");
};
</script>