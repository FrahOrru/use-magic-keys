<script setup>
import { useMagicKeys } from '@vueuse/core'

const text = ref('');

let sec = ref(0);
onMounted(() => {
    timer();
})

function timer(){
    var timer = setInterval(function(){
        document.getElementById('safeTimerDisplay').innerHTML= sec.value;
        sec.value++;
        if (sec < 0) {
            clearInterval(timer);
        }
    }, 1000);
}

const { current, escape } = useMagicKeys({
    passive: false,
    onEventFired(e) {
        e.preventDefault()
        if(e.key !== 'Escape') {
            text.value += e.key;
        }
  },
});

watch(escape, (v) => {
  if (v) {
    navigateTo({ path: '/' })
    sec.value = 0;
    text.value = '';
    timer();
  }
})

</script>
<template>
    <div>
        <h1 id="safeTimerDisplay" class="text-5xl text-center fra-timer"></h1>
        <div class="fra-container">
            <TypingBox></TypingBox>
        </div>

        <div>
            <TypedLetters></TypedLetters>
        </div>

        <!-- <h1 class="text-2xl text-center fra-timer">{{ text }}</h1> -->
    </div>
    
</template>
<style scoped>
    .fra-container {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    .fra-timer {
        padding: 5%;
        color: #ffefcd
    }
</style>