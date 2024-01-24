<template>
  <LayoutComp>
    <template #header>
      <HeaderComp />
    </template>
    <template #resume>
      <Resume :label="label" :amount="amount" :totalAmount="20000">
        <template #graphic> graphic </template>
        <template #action>
          <ActionComp/>
        </template>
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
import ActionComp from "./ActionComp.vue";

export default {
  components: {
    LayoutComp,
    HeaderComp,
    Resume,
    Movements,
    ActionComp
},
  data() {
    return {
      amount: null,
      movs: [{
        id: 0,
        title: "Movimiento",
        description: "Antes de ganar casinl",
        amount: 1000
      },{
        id: 1,
        title: "Paga",
        description: "Delivery diario",
        amount: -240000
      },{
        id: 2,
        title: "HAYSGHA",
        description: "Amgocamaramesi sdt asser",
        amount: 1400
      }
    ]
    };
  },
};
</script>
