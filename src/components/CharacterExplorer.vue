<template>
    <div>
        <div class="character-container">
            <div><img :src="'/profile_img/character/'+selCharacter+'/'+imgType+'_'+imgNumber+'.png'"></div>
        </div>
        <div class="character-selector">
            <div class="hitokage" @click="chnageCharacter('hitokage')" @touchstart="chnageCharacter('hitokage')"></div>
            <div class="charizard" @click="chnageCharacter('charizard')" @touchstart="chnageCharacter('charizard')"></div>
            <div class="squirtle" @click="chnageCharacter('squirtle')" @touchstart="chnageCharacter('squirtle')"></div>
            <div class="blastoise" @click="chnageCharacter('blastoise')" @touchstart="chnageCharacter('blastoise')"></div>
            <div class="bulbasaur" @click="chnageCharacter('bulbasaur')" @touchstart="chnageCharacter('bulbasaur')"></div>
            <div class="venusaur" @click="chnageCharacter('venusaur')" @touchstart="chnageCharacter('venusaur')"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: '',
        props: [
            'state'
        ],
        data(){
            return{
                selCharacter: 'charizard',
                activeClass: 'charizard-normal',
                imgNumber:1,
                imgType:'normal_right',
                interval: {},
                characters:{
                    hitokage: { normalMaxCnt: 3, runMaxCnt: 6 },
                    charizard: { normalMaxCnt: 7, runMaxCnt: 4 },
                    squirtle: { normalMaxCnt: 3, runMaxCnt: 6 },
                    blastoise: { normalMaxCnt: 7, runMaxCnt: 8 },
                    bulbasaur: { normalMaxCnt: 3, runMaxCnt: 5 },
                    venusaur: { normalMaxCnt: 3, runMaxCnt: 5 },
                }
            }
        },
        methods:{
            chnageCharacter(character){
                this.selCharacter = character;
            },
            ChangeFormNormal(){
                this.imgNumber = 1
                this.imgType = 'normal_right'
                var self = this
                clearInterval(self.interval)
                self.interval = setInterval(function () {
                    if(self.imgNumber >= self.characters[self.selCharacter].normalMaxCnt){
                        self.imgNumber = 1;
                    }
                    self.imgNumber = self.imgNumber+1;
                },150)
            },
            ChangeFormRunLeft(){
                this.imgNumber = 1
                this.imgType = 'run_left'
                var self = this
                clearInterval(self.interval)
                self.interval = setInterval(function () {
                    if(self.imgNumber >= self.characters[self.selCharacter].runMaxCnt){
                        self.imgNumber = 1;
                    }
                    self.imgNumber = self.imgNumber+1;
                },150)
            },
            ChangeFormRunRight(){
                this.imgNumber = 1
                this.imgType = 'run_right'
                var self = this
                clearInterval(self.interval)
                self.interval = setInterval(function () {
                    if(self.imgNumber >= self.characters[self.selCharacter].runMaxCnt){
                        self.imgNumber = 1;
                    }
                    self.imgNumber = self.imgNumber+1;
                },150)
            }
        },
        watch:{
            state(newState){
                var self = this
                switch (newState) {
                    case 'default' :
                        this.ChangeFormNormal()
                        break;
                    case 'left' :
                        this.ChangeFormRunLeft()
                        break;
                    case 'right' :
                        this.ChangeFormRunRight()
                        break;
                }
            }
        },
        mounted: function () {

        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    @media screen and (min-width: 300px) and (max-width: 800px) {
        .character-container{
            position: absolute;
            bottom:0;
            margin-left:17%;
            z-index: 8000;
            width:300px;
            height: 300px;
        }
    }

    @media screen and (min-width: 800px) and (max-width: 2920px) {
        .character-container{
            position: absolute;
            bottom:0;
            margin-left:42%;
            z-index: 8000;
            width:300px;
            height: 300px;
        }
    }

    .character-selector{
        position: absolute;
        top:0;
        margin-left:0%;
        z-index: 9999;
        width:500px;
        height: 100px;
    }

    .character-selector .hitokage{
        display: inline-block;
        cursor: pointer;
        z-index: 9999;
        width:50px;
        height: 50px;
        background: url("../assets/profile_img/selector/hitokage.png");background-size: 100% 100%;
    }

    .character-selector .charizard{
        display: inline-block;
        cursor: pointer;
        z-index: 9999;
        width:50px;
        height: 50px;
        background: url("../assets/profile_img/selector/charizard.png");background-size: 100% 100%;
    }

    .character-selector .squirtle{
        display: inline-block;
        cursor: pointer;
        z-index: 9999;
        width:50px;
        height: 50px;
        background: url("../assets/profile_img/selector/squirtle.png");background-size: 100% 100%;
    }

    .character-selector .blastoise{
        display: inline-block;
        cursor: pointer;
        z-index: 9999;
        width:50px;
        height: 50px;
        background: url("../assets/profile_img/selector/blastoise.png");background-size: 100% 100%;
    }

    .character-selector .bulbasaur{
        display: inline-block;
        cursor: pointer;
        z-index: 9999;
        width:50px;
        height: 50px;
        background: url("../assets/profile_img/selector/bulbasaur.png");background-size: 100% 100%;
    }

    .character-selector .venusaur{
        display: inline-block;
        cursor: pointer;
        z-index: 9999;
        width:50px;
        height: 50px;
        background: url("../assets/profile_img/selector/venusaur.png");background-size: 100% 100%;
    }


</style>
