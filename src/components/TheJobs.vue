<template>
		<main
			v-for="job in Jobs"
			:key="job.name"
			class="py-5 text-center hover:bg-gray-600 hover:text-white"
		>
			<hr>
			<h1>{{ job.name }}</h1>
			<p>
				{{ job.location }} | <span class="font-bold">{{ formatToCurrency(job.salary) }}
				</span>
			</p>
		</main>
</template>

<script lang="ts" setup>
import Job from '../types/Job';
import {ref} from 'vue';


const Jobs = ref<Job[]>([
  {id: '1213e', name: 'Chef Martabak', location: 'Cisaga', salary: 50000},
  {id: '12fsf', name: 'Chef NasGor', location: 'Alun-Alun Cisaga', salary: 55000},
  {id: '454tfe', name: 'Mie Ayam Creator', location:'Terminal', salary: 46000},
  {id: '6uhsgfs', name: 'Driver Angkot', location: 'Cisaga', salary:65000}
])

const formatToCurrency = (amount: number) => {
  return "Rp. " + amount.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$&,");
};

</script>