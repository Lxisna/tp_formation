<script>
export default {
  data() {
    return { score: 91 };
  },
  props: {},
};
</script>

<template v-mode="score">
  <div v-if="score <= 50">Disqualification</div>
  <div v-else-if="50 < score && score <= 60">Qualification</div>
  <div v-else-if="60 < score && score <= 90">Good</div>
  <div v-else>Excellent</div>
</template>
