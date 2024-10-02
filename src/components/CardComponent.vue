<script setup>
import ListComponent from './ListComponent.vue';
import FormComponent from './FormComponent.vue'
import { ref, onMounted } from 'vue';

const listData = ref([]);

onMounted(() => {
    const getData = localStorage.getItem('todo-list');
    const parsedData = JSON.parse(getData);
    if (Array.isArray(parsedData)) {
        listData.value = parsedData;
    }
});


</script>

<template>
    <div class="flex min-h-screen justify-center items-center">
        <div class="bg-gray-100 p-6 rounded-lg shadow-lg mx-6 md:mx-0 lg:mx-0 xl:mx-0">
            <h1 class="text-2xl font-bold mb-4">Todo.</h1>
            <p class="text-gray-700 mb-4">Tambahkan todo sesuai keinginan anda.</p>

            <ListComponent :listData="listData" />

            <FormComponent v-model:listData="listData" />
        </div>
    </div>
</template>