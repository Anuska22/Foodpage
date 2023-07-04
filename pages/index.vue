<template>
 <div>
  <section class="loading " v-if="pending">
    <img src="~/assets/images/loading.gif " width="220" alt="">
  </section>
  <section v-else>
    <div class="container">
      <div class="form-group">
          <label for="" class="from-label text-white">Select category</label>
        <select 
        class="from-select from-select-lg border w-full"
        v-model="name"
        @change="getUrl(name)">
          <option selected>Select one</option>
          <option :value="category.strCategory"
          v-for="(category,index) in categoryData.categories" :key="index">{{ category.strCategory }}</option>
        </select>
      </div>
    </div>
    <div class="container grid sm:grid-cols-2  md:grid-cols-2 lg:grid-cols-4 gap-3 py-3">
    <div v-for="(p, index) in data.meals" :key="index">
      <NuxtLink :to="`products/${p.idMeal}`">
        <Productcard :product="p"/>  
      </NuxtLink>
    </div>
   </div>
  </section>
 
 </div>
  </template>

<script setup>
let name ="seafood"
  const url = ref(
    "https://www.themealdb.com/api/json/v1/1/filter.php?c=Seafood"
    );
    const { data: categoryData } = await useFetch(`https://www.themealdb.com/api/json/v1/1/categories.php`);
    const {data, pending} = useFetch(url, {refetch: true });
    
    function getUrl(category) {
     url.value=`https://www.themealdb.com/api/json/v1/1/filter.php?c=${category}`
    };
  

</script>

<style >
.loading {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>