<template>
  <LayoutComp>
    <template #header>
      <HeaderComp />
    </template>
    <template #resume>
      <Resume :label="label" :amount="amount" :totalAmount="20000">
        <template #graphic> graphic </template>
        <template #action> action </template>
      </Resume>
    </template>
    <template #movements>
      <Movements />
    </template>
  </LayoutComp>
</template>
<script>
import HeaderComp from "./HeaderComp.vue";
import LayoutComp from "./LayoutComp.vue";
import Resume from "./Resume/IndexComp.vue";
import Movements from "./Movements/IndexMov.vue";

export default {
  components: {
    LayoutComp,
    HeaderComp,
    Resume,
    Movements,
  },
  data() {
    return {
      amount: null,
    };
  },
};
</script>
