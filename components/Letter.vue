<script setup>
const props = defineProps({
    current: String,
    randomPosition: Boolean
})

let letter;

onMounted(() => {
    if(props.randomPosition) {
        letter = document.getElementById('letter');

        const randomTop = getRandomNumber(0, 20);
        const randomRight = getRandomNumber(0, 100);

        letter.classList.add('absolute');

        letter.style.top = randomTop + '%'
        letter.style.right = randomRight + '%'
    }
})

function getRandomNumber(min, max) {
    return Math.random() * (max - min) + min;
}  

</script>
<template>
    <div :value="current" id="letter" class="p-2 fra-letter h-12 text-center flex items-center justify-center text-3xl">
        {{ current }}
    </div>
</template>

<style scoped>
.fra-letter {
    color: #ffefcd;
    background-color: rgba(255, 255, 255, 0.3);
}
</style>