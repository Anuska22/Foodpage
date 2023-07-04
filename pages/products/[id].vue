<template>
    <div class="container m-auto py-3 grid grid-cols-4 gap-3">
        
        <div >
            <img :src="meal.meals[0].strMealThumb " class="rounded" alt="" />
        </div>
      
        <div class="lg:col-span-3 sm:col-span-4">
            <h1 class="font-bold py-3 text-3xl">
                {{ meal.meals[0].strMeal }}
            </h1>
            <p>
                {{ meal.meals[0].strInstructions }}
            </p>
            <div class="py-3">
                <button class="text-white rounded-md py-2 px-3 bg-red-600">
                    <a :href="meal.meals[0].strYoutube" target="_blank">Watch on YOUTUBE</a>
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
const route = useRoute();

const { data: meal } = await useFetch(
    `https://www.themealdb.com/api/json/v1/1/lookup.php?i=${route.params.id}`
);
</script>

<style lang="scss" scoped></style>