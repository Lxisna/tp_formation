<script setup>
import ComponentData from "./components/ComponentData.vue";
import ComponentProps from "./components/ComponentProps.vue";
import ComponentIfElseVue from "./components/ComponentIfElse.vue";

const greeting = "☺ Thanks !";
</script>

<template>
  <ComponentData />

  <ComponentProps :msg="greeting" />

  <ComponentIfElseVue />
</template>

<style scoped></style>
