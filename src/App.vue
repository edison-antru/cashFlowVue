<template>
  <Suspense>
    <template #default>
      <HomeComp></HomeComp>
    </template>
    <template #fallback>
      <SplashScreen></SplashScreen>
    </template>
  </Suspense>
</template>

<script>
import SplashScreen from "@/components/SplashScreen.vue";
import { defineAsyncComponent } from "vue";

export default {
  components: {
    SplashScreen,
    HomeComp: defineAsyncComponent(
      () =>
        new Promise((resolve) => {
          setTimeout(() => {
            resolve(import("./components/HomeComp.vue"));
          });
        }, 2500)
    ),
  },
};
</script>

<style>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}
* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
