<template>
  <div class="splashScreen">
    <img src="@/assets/cashflow-icon.svg" alt="logo" />
    <h1><span>Splash</span> Screen</h1>
  </div>
</template>

<script></script>

<style scoped>
.splashScreen {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}
h1 {
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
</style>
