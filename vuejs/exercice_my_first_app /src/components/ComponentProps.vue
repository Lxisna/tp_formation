<!-- COMPOSITION
  
  <script setup>
const propos = defineProps({
  msg: String,
});
console.log(propos.msg);
</script>

<template>
  <p>Enjoy your shopping {{ msg }}</p>
</template> -->

<!--////////////////////////////////////////
   POSITION -->
<script>
export default {
  props: {
    msg: {
      type: String,
    },
  },
};
</script>

<template>
  <p>Enjoy your shopping {{ msg }}</p>
</template>
