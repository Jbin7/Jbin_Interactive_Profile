<template>
    <div class="profile_background_img">

    </div>
</template>

<script>
    export default {
        name: '',
        components:{},
        data(){
            return{

            }
        },
        props: {

        },
        methods:{

        },
        mounted: function () {

        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


    @media screen and (min-width: 300px) and (max-width: 800px) {
        .profile_background_img{
            background:url('../assets/profile_img/background/1.png') no-repeat center top;

            -webkit-background-size: cover;
            -moz-background-size: cover;
            -o-background-size: cover;
            -ms-: cover;

            witdh:100%;
            height: 100vh;
        }
    }

    @media screen and (min-width: 800px) and (max-width: 2920px) {
        .profile_background_img{
            background:url('../assets/profile_img/background/1.png') no-repeat center top;

            -webkit-background-size: cover;
            -moz-background-size: cover;
            -o-background-size: cover;
            -ms-: cover;

            witdh:100%;
            height: 100%;
            background-size: 100%;
        }
    }
</style>
