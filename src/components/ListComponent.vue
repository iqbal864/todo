<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    listData: Array,
});

const hapusItem = (index) => {
    props.listData.splice(index, 1);
}

</script>

<template>
    <ul class="mb-4">
        <li v-for="(list, index) in props.listData"
            class="flex justify-between items-center p-2 mb-2 rounded-md bg-white hover:bg-gray-50 transition">
            <span>{{ list }}</span>
            <button @click="hapusItem(index)"
                class="bg-red-100 text-red-500 hover:bg-red-500 hover:text-white p-1 rounded transition focus:outline-none">
                X
            </button>
        </li>
    </ul>
</template>