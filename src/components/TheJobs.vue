<template>
		<ListJob :jobs="Jobs" />
</template>

<script lang="ts" setup>
import Job from '../types/Job';
import ListJob from './ListJob.vue';
import {ref} from 'vue';


const Jobs = ref<Job[]>([
  {id: '1213e', name: 'Chef Martabak', location: 'Cisaga', salary: 50000},
  {id: '12fsf', name: 'Chef NasGor', location: 'Alun-Alun Cisaga', salary: 55000},
  {id: '454tfe', name: 'Mie Ayam Creator', location:'Terminal', salary: 46000},
  {id: '6uhsgfs', name: 'Driver Angkot', location: 'Cisaga', salary:65000}
])

</script>