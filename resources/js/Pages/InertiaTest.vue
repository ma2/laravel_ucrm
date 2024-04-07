<script setup>
import { Link } from "@inertiajs/vue3";
import { ref } from "vue";

const newTitle = ref("");
const newContent = ref("");
</script>

<template>
    Inertiaテストです<br />
    <p><a href="/">a要素でWelcomeに移動</a></p>
    <p><Link href="/">Link部品でWelcomeに移動</Link></p>
    <p><Link :href="route('inertia.index')">名前付きルート</Link></p>
    <p>
        <Link :href="route('inertia.show', { id: 100 })">ルートパラメータ</Link>
    </p>
    <br />
    <div class="mb-8">
        <input type="text" name="newTitle" v-model="newTitle" /> {{ newTitle
        }}<br />
        <input type="text" name="newContent" v-model="newContent" />
        {{ newContent }}<br />
        <Link
            as="button"
            method="post"
            :href="route('inertia.store')"
            :data="{ title: newTitle, content: newContent }"
            >保存テスト</Link
        >
    </div>
</template>
