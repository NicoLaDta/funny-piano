<template>
    <div class="Emoji">
        <img src="" class="Image-emo" alt="">
    </div>
</template>

<script>
import { GiphyFetch } from '@giphy/js-fetch-api'
export default {
    data() {
        return {
            gifs: []
        }
    },
    methods: {
        async takeEmo() {
            const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
            const { data: gifs } = await gf.emoji({ limit: 50 })
            const nbRandom = Math.floor(Math.random() * Math.floor(25));
            const urlRandom = gifs[nbRandom].images['fixed_width'].webp;
            document.querySelector('.Image-emo').src = urlRandom;
            console.log(urlRandom)
        }
    }
}
</script>

<style lang="postcss" scoped>
.Emoji {
    height: 280px;
}

.Image-emo {
    margin: auto;
    padding-top: 8rem;
}
</style>