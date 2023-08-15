<template>
    <div class="relative">
  <div class="flex items-center justify-between bg-gray-50 rounded-md shadow-md py-2 px-1 cursor-pointer" @click="isOpen = !isOpen">
    <div class="pr-3">{{city||'City Name'}}</div>
    <div id="icon">
      <svg
        :class="{'transform rotate-180': isOpen}"
        xmlns="http://www.w3.org/2000/svg"
        class="h-5 w-5 text-gray-600"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M19 9l-7 7-7-7"
        />
      </svg>
    </div>
  </div>
  <div v-if="isOpen" id="dropdown" class="absolute bg-white mt-1 w-full rounded-md shadow-md">
    <div v-for="option in options" :value="option" :key="option" class="py-2 px-4 cursor-pointer" @click="fetchData(option)">{{ option }}</div>
  </div>
</div>

</template>



<script setup>
import { ref, onMounted } from 'vue';
const isOpen=ref(false);
const temp=ref("");
const condition=ref("");
const options=ref(['Lahore','London','New Delhi','Karachi']);
const city=ref("");


const fetchData = async (location) => {
    city.value=location;
    isOpen.value=!isOpen.value;
    const url=`http://api.weatherapi.com/v1/current.json?key=1c2eb9c7a6254332870103529231508&q=${location}&aqi=no`
  try {
    const response = await fetch(url);
    const result = await response.text();
    const data=JSON.parse(result);

    // console.log(data);
    // console.log(data.current);
    // condition.value=result.condition.text;
  } catch (error) {
    console.error(error);
  }
};
onMounted(() => {
    
    
})

</script>

