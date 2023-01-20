<script setup>
    import { useMagicKeys } from '@vueuse/core'
    
    const { current, escape } = useMagicKeys()
    const keys = computed(() => Array.from(current))
</script>
<template>
    <div>
        <div class="fra-color m-5" v-if="keys.length && keys[0] !== 'escape'">
            <Letter :random-position="true" :current="keys[0]"></Letter>
        </div>
    </div>
</template>

<style scoped>
.fra-color {
    color: #ffefcd
}
</style>