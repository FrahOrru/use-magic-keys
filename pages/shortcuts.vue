<script setup>
const blocks = ref([1])
const { current, escape, shift_d, arrowright, arrowleft, control_x} = useMagicKeys()
const keys = computed(() => Array.from(current))

watch(escape, (v) => {
  if (v) {
    navigateTo({ path: '/' })
    timer();
  }
})

watch(shift_d, (v) => {
  if (v) {
    blocks.value.push(blocks.value.length)
  }
})

watch(control_x, (v) => {
  if (v) {
    blocks.value = blocks.value.slice(1);
  }
})

watch(arrowright, (v) => {
  if (v) {
    for(let item of blocks.value) {
        console.log(blocks.value, item)
        var posLeft = document.getElementById(item.toString()).offsetLeft;

        document.getElementById(item.toString()).style.marginLeft  = (posLeft+28)+"px";
    }
  }
})

watch(arrowleft, (v) => {
  if (v) {
    
  }
})
</script>
<template>
    <div>
        <ul class="flex justify-around align-center flex-wrap pb-12">
            <li class="fra-color text-xl"><Letter :random-position="false" :current="'SHIFT+D'"></Letter> add new block</li>
            <li class="fra-color text-xl"><Letter :random-position="false" :current="'arrowright'"></Letter> move the block right</li>
            <li class="fra-color text-xl"><Letter :random-position="false" :current="'CTRL+X'"></Letter> delete block</li>   
        </ul>

        <div class="flex justify-around">
            <div :id="block" class="fra-block w-12 h-12" v-for="block in blocks"></div>
        </div>
    </div>
</template>
<style scoped>
.fra-block {
    background-color: #a58e74;
}
.fra-color {
    color: #ffefcd;
}
</style>