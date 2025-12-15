<template>
    <a :href="link" class="text-white sinEstilo"><i :class="name"></i></a>
</template>

<script setup>
const props = defineProps({
    link: {
        type: String,
    },
    name: {
        type: String,
    }
});
</script>

<style scoped>
.sinEstilo {
    color: #FFFFFF;
    text-decoration: none;
    font-weight: 400;
    font-size: 20px;
}
</style>