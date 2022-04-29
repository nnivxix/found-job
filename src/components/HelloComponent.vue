<template>
  <p>hello {{ name }} </p>
  <button @click="changeName('Han')">
    change name
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: 'HelloComponent',
  data() {
    return {
      name: 'Hanasa',
      age: 12
    }
  },
  methods: {
    changeName(name :string) {
      this.name = name;
      return name;
    },
  },
})
</script>