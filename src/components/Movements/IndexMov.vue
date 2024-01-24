<template>
  <div class="movements">Movements</div>
  <h2 class="title"></h2>
  <div class="content">
    <div v-for="movs in movements" :key="movs.id">\
      {{ movs.title }}
    </div>
  </div>
</template>

<script setup >
import { defineProps,  toRefs } from 'vue';

const props = defineProps({
  movements: {
    type: Array,
    dafault: () => [], 
  }
});

const movements = toRefs(props); //hacer reactiva movements
</script>