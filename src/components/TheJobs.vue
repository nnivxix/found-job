<template>
    <div class="flex justify-center">
      <button class="m-3 bg-purple-500 text-purple-100 py-2 px-4 font-semibold  border-2 border-purple-800 rounded-md" @click="OrderHandle('name')">
        Order By Name
      </button>
      <button class="m-3 bg-purple-500 text-purple-100 py-2 px-4 font-semibold  border-2 border-purple-800 rounded-md" @click="OrderHandle('salary')">
        Order By Salary
      </button>
      <button class="m-3 bg-purple-500 text-purple-100 py-2 px-4 font-semibold  border-2 border-purple-800 rounded-md" @click="OrderHandle('location')">
        Order By Location
      </button>
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
  {id: '1213e', name: 'Chef Martabak', location: 'Cisaga', salary: 50000, description: 'Martabak (bahasa Arab: مطبق, berarti "terlipat") merupakan sajian yang biasa ditemukan di Arab Saudi (terutama di wilayah Hijaz), Yaman, Indonesia, Malaysia, Singapura, dan Brunei. Bergantung pada lokasinya, nama, dan komposisi martabak dapat bervariasi.'},
  {id: '12fsf', name: 'Chef NasGor', location: 'Alun-Alun Cisaga', salary: 55000, description: 'Nasi goreng adalah sebuah versi Indonesia dan Melayu dari nasi goreng, perbedaan utama dibanding dengan nasi goreng di wilayah lainnya adalah makanan tersebut dimasak memakai kecap manis.Makanan tersebut sering kali disertai dengan bahan-bahan tambahan seperti telur goreng, ayam goreng, sate dan bumbu-bumbu seperti sambal, acar, dan kerupuk.'},
  {id: '454tfe', name: 'Mie Ayam Creator', location:'Terminal', salary: 46000, description: 'Mi ayam, mie ayam atau bakmi ayam adalah hidangan Indonesia yang terbuat dari mie gandum kuning yang dibumbui dengan daging ayam yang biasanya dipotong dadu. Hidangan ini banyak terpengaruh dengan teknik penyajian kuliner yang digunakan dalam hidangan Tiongkok.'},
  {id: '6uhsgfs', name: 'Driver Angkot', location: 'Cisaga', salary:65000, description: 'Dalam transportasi di Indonesia, angkutan kota atau biasa disingkat angkot adalah sebuah transportasi umum jenis taksi bersama dengan rute yang sudah ditentukan. Tidak seperti bus yang mempunyai halte bus sebagai tempat perhentian yang sudah ditentukan, angkutan kota dapat berhenti untuk menaikkan atau menurunkan penumpang di mana saja.'}
])

const OrderHandle = (term : OrderTerm) => {
  order.value = term
}
</script>