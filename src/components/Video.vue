<template>
  <div id="app">
    <d-player :options="options"
              @play="play"
              ref="player">
    </d-player>
  </div>
</template>

<script>
  import VueDPlayer from './DPlay.vue'
  import GitHubBadge from 'vue-github-badge'
  export default {
    data() {
      return {
        options: {
          video: {
            url: 'http://static.smartisanos.cn/common/video/t1-ui.mp4',
            pic: 'http://static.smartisanos.cn/pr/img/video/video_03_cc87ce5bdb.jpg'
          },
          autoplay: false,
          contextmenu: [
              {
                  text: 'GitHub',
                  link: 'https://github.com/MoePlayer/vue-dplayer'
              }
          ]
        },
        player: null,
        }
    },
    mounted() {
      this.player = this.$refs.player.dp
    },
    methods: {
      play() {
        console.log('play callback')
      },
      switchHandle() {
        this.player.switchVideo({
          url: 'http://static.smartisanos.cn/common/video/video-jgpro.mp4'
        })
      }
    },
    components: {
      'd-player': VueDPlayer,
      'github-badge': GitHubBadge
    }
  }
</script>

<style scoped>
  body {
    margin: 0;
    padding: 0;
    text-align: center;
  }
  a {
    color: #42b983;
    text-decoration: none;
  }
  .dplayer {
    width: 800px;
    margin: 50px auto;
  }
  h1 {
    font-size: 54px;
    color: #42b983;
    margin: 30px 0 10px;
  }
  h2 {
    font-size: 22px;
    color: #555;
  }
  @media (max-width: 768px) {
    .dplayer {
      width: 90%;
    }
    h1 {
      font-size: 30px;
    }
    h2 {
      font-size: 16px;
    }
  }
</style>