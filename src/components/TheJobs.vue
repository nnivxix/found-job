<template>
  <div class="flex justify-center">
    <button class="m-3 bg-purple-500 text-purple-100 py-2 px-4 font-semibold  border-2 border-purple-800 rounded-md" @click="OrderHandle('name')">Order By Name</button>
    <button class="m-3 bg-purple-500 text-purple-100 py-2 px-4 font-semibold  border-2 border-purple-800 rounded-md" @click="OrderHandle('salary')">Order By Salary</button>
    <button class="m-3 bg-purple-500 text-purple-100 py-2 px-4 font-semibold  border-2 border-purple-800 rounded-md" @click="OrderHandle('location')">Order By Location</button>
  </div>
    <ListJob :jobs="Jobs" :order="order" />
  

</template>

<script lang="ts" setup>
import {ref} from 'vue';

import Job from '../types/Job';
import OrderTerm from '../types/OrderTerm';

import ListJob from './ListJob.vue';

const order = ref<OrderTerm>('name');
const Jobs = ref<Job[]>([
  {id: '1213e', name: 'Chef Martabak', location: 'Cisaga', salary: 50000},
  {id: '12fsf', name: 'Chef NasGor', location: 'Alun-Alun Cisaga', salary: 55000},
  {id: '454tfe', name: 'Mie Ayam Creator', location:'Terminal', salary: 46000},
  {id: '6uhsgfs', name: 'Driver Angkot', location: 'Cisaga', salary:65000}
])

const OrderHandle = (term : OrderTerm) => {
  order.value = term
}
</script>