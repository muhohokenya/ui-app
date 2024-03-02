<script setup>
import { ref, onMounted } from 'vue'
import axios from "axios";
const el = ref()

onMounted(() => {
   axios.get("http://10.0.135.251:3000/students",{
    headers:{
      "Accept":"application/json",
      "Content-Type":"application/json",
      'Access-Control-Allow-Origin': '*',
    }
  }).then(response=>{
    console.log(response)
  });
})
</script>

<template>
  <div>
    hello public EC2
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
