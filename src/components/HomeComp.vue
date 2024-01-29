<template>
  <LayoutComp>
    <!-- Header -->
    <template #header>
      <HeaderComp />
    </template>

    <!-- Index -->
    <template #resume>
      <Resume :label="label" :amount="amount" :totalAmount="totalamount">
        <template #graphic>
          <GraphicComp :amounts="amounts"></GraphicComp>
        </template>
        <template #action>
          <ActionComp @create="create" />
        </template>
      </Resume>
    </template>

    <!-- List movements -->
    <template #movements>
      <Movements :movements="movements" @remove="remove"/>
    </template>

  </LayoutComp>
</template>
<script>
import HeaderComp from "./HeaderComp.vue";
import LayoutComp from "./LayoutComp.vue";
import Resume from "./Resume/IndexComp.vue";
import Movements from "./Movements/IndexMov.vue";
import ActionComp from "./ActionComp.vue";
import GraphicComp from "./Resume/GraphicComp.vue";

export default {
  components: {
    LayoutComp,
    HeaderComp,
    Resume,
    Movements,
    ActionComp,
    GraphicComp
},
  data() {
    return {
      amount: null,
      label: null,
      totalamount: "1000000",
      movements: [{
        id: 0,
        title: "Movimiento",
        description: "Antes de ganar casinl",
        amount: 100,
        time: new Date("02-01-2024"),
      },{
        id: 1,
        title: "Paga",
        description: "Delivery diario",
        amount: 200,
        time: new Date("02-01-2024"),
      },{
        id: 2,
        title: "HAYSGHA 3",
        description: "Amgocamaramesi sdt asser",
        amount: 500,
        time: new Date("02-01-2024"),
      },{
        id: 3,
        title: "Movimi 4" ,
        description: "Antes de ganar casinl",
        amount: 200,
        time: new Date("02-01-2024"),
      },{
        id: 4,
        title: "Paga 5",
        description: "Delivery diario",
        amount: -400,
        time: new Date("02-01-2024"),
      },{
        id: 5,
        title: "Movimiento 6",
        description: "Antes de ganar casinl",
        amount: -600,
        time: new Date("02-01-2024"),
      },{
        id: 6,
        title: "Paga 7",
        description: "Delivery diario",
        amount: -300,
        time: new Date("02-01-2024"),
      },{
        id: 7,
        title: "Movimiento 8",
        description: "Antes de ganar casinl",
        amount: 100,
        time: new Date("02-01-2024"),
      },{
        id: 8,
        title: "Paga 9",
        description: "Delivery diario",
        amount: 300,
        time: new Date("01-01-2024"),
      },{
        id: 9,
        title: "Movimiento 10",
        description: "Antes de ganar casinl",
        amount: 500,
        time: new Date("01-01-2024"),
      },
    ]
    };
  },
  computed : {
    amounts() {
      const lastDays = this.movements
        .filter( m => {
          const today = new Date();
          const oldDate = today.setDate(today.getDate() - 30);

          return m.time > oldDate
        })
        .map(m => m.amount)

      return lastDays.map((m, i) => {
        const lastMovements = lastDays.slice(0, i);

        return lastMovements.reduce((suma, movement) => {
          return suma + movement
        }, 0);

      }); 
    }
  },
  methods: {
    create(movement) {
      this.movements.push(movement)
    },  
    remove(id) {
      const index = this.movements.findIndex(m => m.id === id);
      this.movements.splice(index, 1);
}
  }
};
</script>
