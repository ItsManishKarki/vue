<script setup>
import { ref , onMounted } from 'vue'
import axios from 'axios';

const apiData =  ref([]);

const api = () =>{
  axios.get('http://192.168.1.26:8000/api/food').then((response)=>{
    console.log(response.data)
  apiData.value = response.data
})
}

onMounted(api)



</script>

<template>
<div v-for=" apiValue in apiData" :key="apiValue.id">
<h1>{{ apiValue.name }}</h1>
<p>{{ apiValue.price }}</p>

</div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
