<template>
  <div class="home">
    <h1>Home</h1>
    <p class="count" v-text="count"></p>
    <div class="buttons">
      <button @click="decreaseCount">−</button>
      <button @click="increaseCount">+</button>
    </div>
    <h3 class="odd-even" v-text="oddOrEven" />
  </div>
</template>

<script setup>
import { ref, computed } from '@vue/reactivity'
const count = ref(0)
const decreaseCount = () => {
  count.value--
}
const increaseCount = () => {
  count.value++
}
const oddOrEven = computed(() => (count.value % 2 === 0 ? 'even' : 'odd'))
</script>

<style>
.home {
  display: grid;
  place-items: center;
  place-content: center;
  grid-gap: 1rem;
}

.count {
  font-size: 8rem;
}

.buttons {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 1rem;
}

.buttons button {
  font-size: 2rem;
  font-weight: bold;
  cursor: pointer;
}
</style>
