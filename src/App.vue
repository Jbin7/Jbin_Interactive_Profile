<template>
  <div id="app">
    <div v-if="browser == 'Internet Explorer'">
      <profile-ie></profile-ie>
    </div>
    <div v-if="browser != 'Internet Explorer'">
      <profile></profile>
    </div>

  </div>
</template>

<script>
  import profile from './views/Profile'
  import profileIe from './views/ProfileExplorer'
    export default {
        name: '',
        components:{
            'Profile': profile,
            'ProfileIe': profileIe
        },
        data(){
            return{
              browser: ''
            }
        },
        props: {

        },
        methods:{

        },
        mounted: function () {
            var agent = navigator.userAgent, match;
            var app, version;

            if((match = agent.match(/MSIE ([0-9]+)/)) || (match = agent.match(/Trident.*rv:([0-9]+)/))) app = 'Internet Explorer';
            else if(match = agent.match(/Chrome\/([0-9]+)/)) app = 'Chrome';
            else if(match = agent.match(/Firefox\/([0-9]+)/)) app = 'Firefox';
            else if(match = agent.match(/Safari\/([0-9]+)/)) app = 'Safari';
            else if((match = agent.match(/OPR\/([0-9]+)/)) || (match = agent.match(/Opera\/([0-9]+)/))) app = 'Opera';
            else app = 'Unknown';

            if(app !== 'Unknown') version = match[1];

            console.log('Browser: ' + app);
            console.log('Version: ' + version);

            this.browser = app;

            if(app == 'Internet Explorer'){
                setTimeout(function () {
                    alert('익스플로러에서는 정상 동작하지 않는 기능이 있을수 있습니다. 크롬 브라우저 사용을 권장합니다.')
                },500)
            }
        }
    }
</script>

<style>
  html, body { width:100%; height:100%; overflow:auto; margin: 0px;}

</style>
