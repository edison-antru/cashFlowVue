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
      <Movements :movements="movs"/>
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
      movs: [{
        id: 0,
        title: "Movimiento",
        amount: 1000
      },{
        id: 1,
        title: "Paga",
        amount: 2400
      },{
        id: 2,
        title: "HAYSGHA",
        amount: 1400
      }
    ]
    };
  },
};
</script>
