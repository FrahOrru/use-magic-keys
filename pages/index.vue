<template>
    <div>
        <h1 class="text-5xl text-center fra-title">Welcome to my useMagicKey demo</h1>

        <ul class="absolute fra-menu rounded-md">
            <li class="py-5 px-12 text-xl rounded-md"><NuxtLink to="/game">Play Keyboard game</NuxtLink></li>
            <li class="py-5 px-12 text-xl rounded-md"><NuxtLink to="/shortcuts">Play with the shortcuts</NuxtLink></li>
        </ul>
    </div>
</template>
<style scoped>
.fra-menu {
    background-color: #a58e74;
    color: #ffefcd;

    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.fra-menu li:hover {
    background-color: #87745f;
}

.fra-title {
        padding: 6%;
        color: #ffefcd
}
</style>