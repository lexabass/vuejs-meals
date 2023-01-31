<template>
  <div class="bg-white shadow-xl rounded-2xl hover:scale-105 transition-all">
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
      <img 
        :src="meal.strMealThumb" 
        :alt="meal.strMeal" 
        class="rounded-t-2xl w-full h-48 object-cover" 
      />
    </router-link>
    <div class="p-5">
      <h3 class="font-bold text-2xl">{{ meal.strMeal }}</h3>
      <p class="text-xl my-4">
        {{ truncateWords(meal.strInstructions, 20) }}
      </p>
      <div class="flex justify-between items-center">
        <YouTubeButton :href="meal.strYoutube">
          YouTube
        </YouTubeButton>
      </div>
    </div>

  </div>
</template>

<script setup>
import { truncateWords } from "../filters/index"
import YouTubeButton from './YouTubeButton.vue';

const { meal } = defineProps({
  meal: {
    required: true,
    type: Object
  }
})

</script>