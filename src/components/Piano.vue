<template>
    <div class="Piano">
        <div class="Piano-container">
            <div class="keys-whites">
                <button class="key-white C" v-on:click="playAudio('/assets/sounds/C.mp3')" 
                v-on:click.exact="keybord('C', 'white')" @mouseout="SecondaryKey('soundC', 'white')"><span class="sound">Do</span></button>
                <button class="key-white D" v-on:click="playAudio('/assets/sounds/D.mp3')" 
                v-on:click.exact="keybord('D', 'white')" @mouseout="SecondaryKey('soundD', 'white')"><span class="sound">Re</span></button>
                <button class="key-white E" v-on:click="playAudio('/assets/sounds/E.mp3')" 
                v-on:click.exact="keybord('E', 'white')" @mouseout="SecondaryKey('soundE', 'white')"><span class="sound">Mi</span></button>
                <button class="key-white F" v-on:click="playAudio('/assets/sounds/F.mp3')" 
                v-on:click.exact="keybord('F', 'white')" @mouseout="SecondaryKey('soundF', 'white')"><span class="sound">Fa</span></button>
                <button class="key-white G" v-on:click="playAudio('/assets/sounds/G.mp3')" 
                v-on:click.exact="keybord('G', 'white')" @mouseout="SecondaryKey('soundG', 'white')"><span class="sound">Sol</span></button>
                <button class="key-white A" v-on:click="playAudio('/assets/sounds/A.mp3')" 
                v-on:click.exact="keybord('A', 'white')" @mouseout="SecondaryKey('soundA', 'white')"><span class="sound">La</span></button>
                <button class="key-white B" v-on:click="playAudio('/assets/sounds/B.mp3')" 
                v-on:click.exact="keybord('B', 'white')" @mouseout="SecondaryKey('soundB', 'white')"><span class="sound">Si</span></button>
            </div>
            <div class="keys-blacks">
                <button class="key-black Cc" v-on:click="playAudio('/assets/sounds/C%23.mp3')" 
                v-on:click.exact="keybord('Cc', 'black')" @mouseout="SecondaryKey('soundCc', 'black')"></button>
                <button class="key-black soundDd" v-on:click="playAudio('/assets/sounds/D%23.mp3')" 
                v-on:click.exact="keybord('Dd', 'black')" @mouseout="SecondaryKey('soundDd', 'black')"></button>
                <button class="key-black Ff" v-on:click="playAudio('/assets/sounds/F%23.mp3')" 
                v-on:click.exact="keybord('Ff', 'black')" @mouseout="SecondaryKey('soundFf', 'black')"></button>
                <button class="key-black Gg" v-on:click="playAudio('/assets/sounds/G%23.mp3')" 
                v-on:click.exact="keybord('Gg', 'black')" @mouseout="SecondaryKey('soundGg', 'black')"></button>
                <button class="key-black Aa" v-on:click="playAudio('/assets/sounds/A%23.mp3')" 
                v-on:click.exact="keybord('Aa', 'black')" @mouseout="SecondaryKey('soundAa', 'black')"></button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        this.vEmoji = this.$parent.$children[0]
        this.start = false
        this.addListeners()
        this.removeListeners()
    },
    methods: {
        playAudio: function(url) {
            console.log(this);
            new Audio(url).play();
            this.vEmoji.takeEmo();
        },

        addListeners() {
            window.addEventListener('keydown', this.OnKeyDown)
            window.addEventListener('keyup', this.OnKeyUp)
        },
        OnKeyDown(e) {
            if (this.start) return
            switch (e.keyCode) {
                case 81:
                    this.playAudio('/assets/sounds/C.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('C')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 83:
                    this.playAudio('/assets/sounds/D.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('D')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 68:
                    this.playAudio('/assets/sounds/E.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('E')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[2].style.color = "#FFFFFF";
                    break;
                case 70:
                    this.playAudio('/assets/sounds/F.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('F')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 71:
                    this.playAudio('/assets/sounds/G.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('G')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 72:
                    this.playAudio('/assets/sounds/A.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('A')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
                case 74:
                    this.playAudio('/assets/sounds/B.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('B')[0].style.backgroundColor = "#FFD12D";
                    document.getElementsByClassName('sound')[6].style.color = "#FFFFFF";
                    break;
                case 90:
                    this.playAudio('/assets/sounds/C%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('Cc')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 69:
                    this.playAudio('/assets/sounds/D%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('Dd')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 84:
                    this.playAudio('/assets/sounds/F%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('Ff')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 89:
                    this.playAudio('/assets/sounds/G%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('Gg')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 85:
                    this.playAudio('/assets/sounds/A%23.mp3');
                    this.vEmoji.takeEmo();
                    document.getElementsByClassName('Aa')[0].style.backgroundColor = "#E6016F";
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
            }
            this.start = true
        },
        OnKeyUp() {
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
        keybord(key, touch) {
            if (touch == 'white') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#FFD12D";
            } else {
                if (touch == 'black') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#E6016F";
                }
            }
            switch (key) {
                case 'C':
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 'D':
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 'E':
                    document.getElementsByClassName('sound')[2].style.color = "#FFFFFF";
                    break;
                case 'F':
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 'G':
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 'A':
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
                case 'B':
                    document.getElementsByClassName('sound')[6].style.color = "#FFFFFF";
                    break;
                case 'Cc':
                    document.getElementsByClassName('sound')[0].style.color = "#FFFFFF";
                    break;
                case 'Dd':
                    document.getElementsByClassName('sound')[1].style.color = "#FFFFFF";
                    break;
                case 'Ff':
                    document.getElementsByClassName('sound')[3].style.color = "#FFFFFF";
                    break;
                case 'Gg':
                    document.getElementsByClassName('sound')[4].style.color = "#FFFFFF";
                    break;
                case 'Aa':
                    document.getElementsByClassName('sound')[5].style.color = "#FFFFFF";
                    break;
                default:
                    break;
            }
        },
        SecondaryKey(key, touch) {
            if (touch == 'black') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#000000";
            } else {
                if (key == 'white') {
                document.getElementsByClassName(key)[0].style.backgroundColor = "#FFFFFF";
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
