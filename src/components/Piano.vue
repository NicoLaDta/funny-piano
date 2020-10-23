<template>
    <div class="Piano">
        <div class="Piano-container">
            <div class="keys-whites">
                <button class="key-white soundC" v-on:click="playAudio('/assets/sounds/C.mp3')" 
                v-on:click.exact="key('soundC', 'white')" @mouseout="backKey('soundC', 'white')">
                <span class="sound">Do</span></button>
                <button class="key-white soundD" v-on:click="playAudio('/assets/sounds/D.mp3')" 
                
                v-on:click.exact="key('soundD', 'white')" @mouseout="backKey('soundD', 'white')">
                <span class="sound">Re</span></button>
                <button class="key-white soundE" v-on:click="playAudio('/assets/sounds/E.mp3')" 
                
                v-on:click.exact="key('soundE', 'white')" @mouseout="backKey('soundE', 'white')">
                <span class="sound">Mi</span></button>
                <button class="key-white soundF" v-on:click="playAudio('/assets/sounds/F.mp3')" 
                
                v-on:click.exact="key('soundF', 'white')" @mouseout="backKey('soundF', 'white')">
                <span class="sound">Fa</span></button>
                <button class="key-white soundG" v-on:click="playAudio('/assets/sounds/G.mp3')" 
                
                v-on:click.exact="key('soundG', 'white')" @mouseout="backKey('soundG', 'white')">
                <span class="sound">Sol</span></button>
                <button class="key-white soundA" v-on:click="playAudio('/assets/sounds/A.mp3')" 
                
                v-on:click.exact="key('soundA', 'white')" @mouseout="backKey('soundA', 'white')">
                <span class="sound">La</span></button>
                <button class="key-white soundB" v-on:click="playAudio('/assets/sounds/B.mp3')" 
                
                v-on:click.exact="key('soundB', 'white')" @mouseout="backKey('soundB', 'white')"><span class="sound">Si</span></button>
            </div>
            <div class="keys-blacks">
                <button class="key-black soundCc" v-on:click="playAudio('/assets/sounds/C%23.mp3')" 
                v-on:click.exact="key('soundCc', 'black')" @mouseout="backKey('soundCc', 'black')"></button>
                <button class="key-black soundDd" v-on:click="playAudio('/assets/sounds/D%23.mp3')" 
                v-on:click.exact="key('soundDd', 'black')" @mouseout="backKey('soundDd', 'black')"></button>
                <button class="key-black soundFf" v-on:click="playAudio('/assets/sounds/F%23.mp3')" 
                v-on:click.exact="key('soundFf', 'black')" @mouseout="backKey('soundFf', 'black')"></button>
                <button class="key-black soundGg" v-on:click="playAudio('/assets/sounds/G%23.mp3')" 
                v-on:click.exact="key('soundGg', 'black')" @mouseout="backKey('soundGg', 'black')"></button>
                <button class="key-black soundAa" v-on:click="playAudio('/assets/sounds/A%23.mp3')" 
                v-on:click.exact="key('soundAa', 'black')" @mouseout="backKey('soundAa', 'black')"></button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        console.log(this)
        this.vEmoji = this.$parent.$children[0]
        this.addListeners()
        this.start = false
    },
    methods: {
        playAudio: function(url) {
            new Audio(url).play();
            this.vEmoji.takeEmo();
        },

        addListeners() {
            window.addEventListener('keydown', this.OnKeyDown)
            window.addEventListener('keyup', this.OnKeyUp)
        },
        OnKeyDown(e) {
            console.log(e)
            if (this.start) return
            switch (e.keyCode) {
                case 81:
                    this.playAudio('/assets/sounds/C.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundC')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 83:
                    this.playAudio('/assets/sounds/D.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundD')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 68:
                    this.playAudio('/assets/sounds/E.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundE')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[2].style.color = "#FFFFFF";
                    break;
                case 70:
                    this.playAudio('/assets/sounds/F.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundF')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 71:
                    this.playAudio('/assets/sounds/G.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundG')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 72:
                    this.playAudio('/assets/sounds/A.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundA')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
                case 74:
                    this.playAudio('/assets/sounds/B.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundB')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[6].style.color = "#FFFFFF";
                    break;
                case 90:
                    this.playAudio('/assets/sounds/C%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundCc')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 69:
                    this.playAudio('/assets/sounds/D%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundDd')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 84:
                    this.playAudio('/assets/sounds/F%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundFf')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 89:
                    this.playAudio('/assets/sounds/G%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundGg')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 85:
                    this.playAudio('/assets/sounds/A%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('soundAa')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
            }
            this.start = true
        },
        OnKeyUp(e) {
            console.log(e)
            this.start = false
            for (let i = 0; i < 7; i++) {
                document.getElementsByClassName('key-white')[i].style.backgroundColor = "#FFFFFF";
            }
            for (let j = 0; j < 5; j++) {
                document.getElementsByClassName('key-black')[j].style.backgroundColor = "#000000";
            }
            for (let k = 0; k < 7; k++) {
                document.getElementsByClassName('sound')[k].style.color = "rgba(255, 255, 255, 0.4)";
            }
        },
        key(key, touch) {
            if (touch == 'white') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#FFD12D";
            } else {
                if (touch == 'black') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#E6016F";
                }
            }
            switch (key) {
                case 'soundC':
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 'soundD':
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 'soundE':
                    document.getElementsByClassName('sound')[2].style.color = "#FFFFFF";
                    break;
                case 'soundF':
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 'soundG':
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 'soundA':
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
                case 'soundB':
                    document.getElementsByClassName('sound')[6].style.color = "#FFFFFF";
                    break;
                case 'soundCc':
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 'soundDd':
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 'soundFf':
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 'soundGg':
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 'soundAa':
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
            }
        },
        backKey(key, touch) {
            if (key == 'white') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#FFFFFF";
            } else {
                if (touch == 'black') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#000000";
                }
            }
            for (let k = 0; k < 7; k++) {
                document.getElementsByClassName('sound')[k].style.color = "rgba(255, 255, 255, 0.4)";
            }
        },
        removeListeners() {
            window.removeEventListener('keydown', this.OnKeyDown)
            window.removeEventListener('keyup', this.OnKeyUp)
        }
    }
}
</script>

<style lang="postcss" scoped>
@media (max-width: 700px) {
    .Piano-container {
        width: 368px;
    }
    .key-white {
        width: 47px;
    }
    .key-black {
        width: 20px;
    }
    .key-black:nth-child(1) {
        left: 49px;
    }
    .key-black:nth-child(2) {
        left: 98px;
    }
    .key-black:nth-child(3) {
        left: 198px;
    }
    .key-black:nth-child(4) {
        left: 248px;
    }
    .key-black:nth-child(5) {
        left: 298px;
    }
}

.keys-whites {
    display: flex;
    margin-top: 0.75rem;
}

.Piano-container {
    flex-direction: column;
    margin: auto;
    display: flex;
    height: 276px;
    width: 531px;
    border-radius: 10px;
    background: black;
    margin-top: 190px;
    margin-bottom: 30px;
    align-items: center;
    filter: drop-shadow(0px 12px 80px rgba(0, 0, 0, 0.3));
}

.key-white {
    height: 252px;
    width: 69px;
    background: white;
    margin: 0px 2px;
}

.key-white:nth-child(1) {
    height: 252px;
    width: 69px;
    background: white;
    border-radius: 5px 0px 0px 5px;
}

.key-white:nth-child(7) {
    height: 252px;
    width: 69px;
    background: white;
    border-radius: 0px 5px 5px 0px;
}

.key-white:focus {
    background: #FFD12D;
}

.keys-blacks {
    display: flex;
    width: 507px;
    margin-top: -252px;
    align-items: flex-start;
}

.key-black {
    height: 184px;
    width: 30px;
    background: #000000;
    border-radius: 0px 0px 5px 5px;
    margin-left: 43px;
}

.key-black:focus {
    background: #E6016F;
}

.key-black:nth-child(1) {
    margin-left: 56px;
}

.key-black:nth-child(2) {
    margin-right: 73px;
}

.sound {
    position: absolute;
    bottom: -50px;
    margin-left: -35px;
    text-transform: uppercase;
    width: 73px;
    color: rgba(255, 225, 225, 0.4);
}
</style>