<script>
export default {
    // Card menerima data title dan description
    props: ['item']
}
</script>

<template>
    <div class="card">
        <h1>{{ item.title }}</h1>
        <p>{{ item.description }}</p>
        <button @click="$emit('deleteFood', item.id)">Delete</button>
    </div>
</template>

<style>
.card {
    padding: 16px;
    border: 1px solid #f0f0f0;
}
</style>
