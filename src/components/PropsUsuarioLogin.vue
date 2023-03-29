<script setup>
    defineProps(["title", "body", "userId", "id"]);
</script>

<template>
    <div class="card">
        <div class="card-body">
            <div class="card-title">{{id}} - {{ title }}</div>
            <p>{{ body }}</p>
        </div>
    </div>
</template>