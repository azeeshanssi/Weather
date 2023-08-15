<template>
    <div id="card" class="bg-gray-200 rounded-lg shadow-md w-1/3 h-3/4 flex flex-col items-center " >
    <div id="header" class="flex flex-col justify-center items-center">
        <h1 class="text-xl font-semibold text-gray-700 mb-2 mt-8">Select City for Weather</h1>
        <Dropdown class="mb-2"></Dropdown>
    </div>
    <div class="flex-grow w-full flex flex-col justify-center items-center">
        <TempDisplay></TempDisplay>
    </div>
    





    </div>
</template>

<script setup>
import Dropdown from './Dropdown.vue'
import TempDisplay from './TempDisplay.vue';


</script>

