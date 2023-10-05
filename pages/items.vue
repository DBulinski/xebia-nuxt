<script setup>
import { ref } from "vue";

const selectedItem = ref(null);
const items = ref(new Array(5000).fill(""));
</script>

<template>
  <strong v-if="selectedItem !== null"
  >Selected item is {{ selectedItem + 1 }}</strong
  >
  <div class="items-container">
    <div class="item" v-for="(_, index) in items">
      <button
          v-bind:disabled="selectedItem === index"
          @click="selectedItem = index"
      >
        Index {{ index + 1 }}
      </button>
    </div>
  </div>
</template>

<style>
.items-container {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.item {
  flex: 1;
}
</style>
