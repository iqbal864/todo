<script setup>
import { ref, defineProps } from 'vue';

const props = defineProps({
    listData: Array
});

const inputData = ref('');

const handleTambah = (e) => {
    e.preventDefault();

    if (inputData.value !== '') {
        props.listData.push(inputData.value);
        localStorage.setItem('todo-list', JSON.stringify(props.listData));
        inputData.value = '';
    }

}

const capitalizeFirst = () => {
    if (inputData.value && inputData.value.length > 0) {
        inputData.value = inputData.value.charAt(0).toUpperCase() + inputData.value.slice(1);
    }
}
</script>

<template>
    <form @submit="handleTambah">
        <input type="text" placeholder="Masukkan todo..." v-model="inputData" @input="capitalizeFirst"
            class="w-full p-2 mb-4 border border-gray-300 rounded-md" />
        <button type="submit" class="w-full bg-blue-500 text-white p-2 rounded-md hover:bg-blue-600">
            Tambah
        </button>
    </form>
</template>