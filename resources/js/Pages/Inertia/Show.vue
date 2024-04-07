<script setup>
import { router } from "@inertiajs/vue3";

defineProps({
    id: String,
    blog: Object,
});

const deleteConfirm = (id) => {
    console.log(id);
    router.delete(`/inertia/delete/${id}`, {
        onBefore: () => confirm("本当に削除しますか?"),
    });
};
</script>
<template>
    <div>{{ id }}</div>
    <div>{{ blog.title }}</div>
    <button @click="deleteConfirm(id)">削除</button>
</template>
