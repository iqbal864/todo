<script setup>
import ListComponent from './ListComponent.vue';
import FormComponent from './FormComponent.vue'
import { ref } from 'vue';

const listData = ref([]);

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