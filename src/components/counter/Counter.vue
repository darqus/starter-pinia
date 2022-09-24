<template>
  <p class="count" v-text="storeCounter.count"></p>
</template>

<script setup>
import { useCounterStore } from '../../stores/counter'

const storeCounter = useCounterStore()
</script>
