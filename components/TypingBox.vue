<script setup>
    const { data } = await useFetch('https://api.quotable.io/random');
</script>
<template>
    <div class="fra-bg p-5 w-96 h-full rounded-md"> 
        <div class="fra-maintxt pb-5 text-lg">{{ data?.content }}</div>
    </div>
</template>
<style scoped>
.fra-bg {
    background-color: #a58e74;
    color: #ffefcd
}
</style>