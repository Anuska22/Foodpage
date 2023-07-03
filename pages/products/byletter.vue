<template>
    <div  class="container py-4">
      <div class="loading" v-if="pending">
        <img src="~/assets/images/loading.gif"  alt="">
      </div>
     <div v-else>
        <label for="">Search Items By First Letter</label>
       <input type="text" v-model="ch" class="border-black" maxlength="1" />
       <button @click="geturl(ch) " class="px-3 py-1 rounded mx-3 bg-blue-500">
        Search
        </button>
        <div class="container grid lg:grid-cols-4 sm:grid-cols-1 gap-3 py-3">
    <div v-for="(p, index) in items.meals" :key="index">
      <NuxtLink :to="`/products/${p.idMeal}`">
        <Productcard :product="p"/>  
      </NuxtLink>
    </div>
   </div>
    </div>
    </div>
</template>

<script setup>
const ch  =ref("a");
const url = ref("https://www.themealdb.com/api/json/v1/1/search.php?f=a");
const {data : items, pending} = await useFetch( url, {refetch: true});

function geturl(ch) {
    url.value = `https://www.themealdb.com/api/json/v1/1/search.php?f=${ch}`
};
</script>

<style >

</style>