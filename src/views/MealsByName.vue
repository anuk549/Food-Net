<template>
  <div class="p-8 bg-0">
    <h1 class="text-4xl font-bold mb-4 text-orange-500">Search Meals by Name</h1>
  </div>
  <div class="px-8 pb-3">
        <input type="text" 
        class="rounded border-2  border-gray-200 w-full" 
        placeholder="Search for Meals" 
        v-model="keyword"
        @change="searchMeals"
        />
    </div>
          <Meals :meals="meals" />

</template>

<script setup>
import { computed } from "@vue/reactivity";
import { onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import store from "../store";
import Meals from '../components/Meals.vue'
import YouTubeButton from "../components/YouTubeButton.vue";

const route = useRoute();
const keyword = ref("");
const meals = computed(() => store.state.searchedMeals)



function searchMeals() {
   
    store.dispatch("searchMeals", keyword.value)
  
}

onMounted(() => {
  keyword.value = route.params.name
  if (keyword.value) {
    searchMeals()
  }
})
</script>