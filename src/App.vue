<template>
    <div id="app">
        <TitleP></TitleP>
        <emoji></emoji>
        <piano></piano>
    </div>
</template>

<script>
import TitleP from '@/components/TitleP'
import Emoji from '@/components/Emoji'
import Piano from '@/components/Piano'
export default {
    name: 'App',
    components: {
        TitleP,
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

@media (max-width: 700px) {
    #app {
        justify-content: space-around;
    }
}
</style>