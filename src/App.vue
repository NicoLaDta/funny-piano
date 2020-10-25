<template>
    <div id="app">
        <h1 class="title">The emoji piano</h1>
        <emoji></emoji>
        <piano></piano>
    </div>
</template>

<script>
import Emoji from '@/components/Emoji'
import Piano from '@/components/Piano'
export default {
    name: 'App',
    components: {
        Emoji,
        Piano,
    }
}
</script>

<style lang="postcss" scoped>
#app {
    text-align: center;
    margin: auto;
    padding-top: 2.5rem;
    width: 100%;
    height: 100%;
    font-family: 'PT Mono', monospace;
    min-height: 100vh;
    background: linear-gradient(135deg, #FF9D6C 0%, #BB4E75 100%);
}

.title {
    @apply bg-black text-white;
    height: 60px;
    width: 332px;
    margin: auto;
    padding-top: 0.5rem;
    border-radius: 10px;
    font-size: 30px;
}

@media (max-width: 700px) {
    #app {
        justify-content: space-around;
    }
}
</style>