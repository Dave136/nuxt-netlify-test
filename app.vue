<script setup>
const info = ref(null);

async function showData() {
  const { data } = await useFetch("/api/greetings")
  info.value = data;
}
</script>

<template>
  <div>
    <button @click="showData">load data</button>
    <pre v-if="info">{{ info }}</pre>
  </div>
</template>
