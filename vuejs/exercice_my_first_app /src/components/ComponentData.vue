<!-- COMPOSITION

<script setup>
import { ref, onMounted } from "vue";

// reactive state 反应式系统
const count = ref(0);

// functions that mutate state and trigger updates
function add() {
  count.value++;
}

function remove() {
  count.value--;
}
</script>
<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ count }} items in the shopping bag</p>
    <button @click="add">ADD</button>
    <button @click="remove">REMOVE</button>
  </div>
</template>
-->

<!--////////////////////////////////////////
   OPTION -->
<script>
export default {
  data() {
    return { message: "Add to your bag!", count: 0 };
  },
  methods: {
    add() {
      this.count++;
    },
    remove() {
      this.count--;
    },
  },
};
</script>

<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ count }} items in the shopping bag</p>
    <button @click="add">ADD</button>
    <button @click="remove">REMOVE</button>
  </div>
</template>
