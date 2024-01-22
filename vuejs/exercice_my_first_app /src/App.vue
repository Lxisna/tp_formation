<script setup>
import ComponentData from "./components/ComponentData.vue";
import ComponentProps from "./components/ComponentProps.vue";
import ComponentIfElseVue from "./components/ComponentIfElse.vue";
import ComponentFormVue from "./components/ComponentForm.vue";

const greeting = "☺ Thanks !";
</script>

<template>
  <ComponentData />

  <ComponentProps :msg="greeting" />

  <ComponentIfElseVue />

  <ComponentFormVue />
</template>

<style scoped></style>
