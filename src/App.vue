<template>
  <div id="app">
    <!-- topbar -->
    <div class="topBar">
      <b-container fluid="sm">
        <div class="flex alignCenter">
          <img alt="batgame logo" src="./assets/batgame.png" class="batgame">
          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
          <div id="topBarRight" class="flex gap24">
            <div>
              <span class="title" style="display: block;">Nomor Ponsel</span>
              <span class="subtitle" style="display: block; font-weight: bold;">08123456789</span>
            </div>
            <div class="flex alignCenter gap">
              <CurrencyDollarIcon  size="2x" style="color: silver;"/>
              <div>
                <span class="title" style="display: block; color: silver;">Token Platinum</span>
                <span class="subtitle" style="display: block; font-weight: bold">1.000.000 Pt</span>
              </div>
              <b-button @click="topUp" class="button title" style="font-weight: bold">TOP UP</b-button>
            </div>
            <div class="flex alignCenter gap">
              <CurrencyDollarIcon  size="2x" style="color: gold;"/>
              <div>
                <span class="title" style="display: block; color: orange;">Winning Platinum</span>
                <span class="subtitle" style="display: block; color: gold; font-weight: bold">1.000.000 Pt</span>
              </div>
              <b-button @click="change" class="btnOrange title" style="font-weight: bold">TUKAR</b-button>
            </div>
          </div>
        </div>
      </b-container>
    </div>
    <!-- Nav -->
    <Navbar />
    <!-- Content -->
    <b-container style="margin-bottom: 100px" >
      <div class="content">
        <h2>{{data.name}} <ShareIcon @click="share"  size="0.75x" class="share"/></h2>
        <div class="flex gap24" style="margin-bottom: 24px;">
          <div class="media">
            <b-img :src="data.thumbnail" fluid alt="Responsive image"></b-img>
          </div>  
          <div class="description">
            <h3>Game description</h3>
            <p>{{data.description}}</p>
            <div>
              <div style="display: flex; gap: 24px">
                <b-button @click="play" class="btnOrange" style="font-weight: bold">PLAY <CurrencyDollarIcon  size="1.5x"/>10</b-button>{{' '}}
                <a :href="data.tutorial_game_url" target="_blank" style="color: inherit; font-size: 20px;">Play Demo</a>
              </div>
            </div>
            </div>  
        </div>
        <div class="flex gap24">
          <div class="media">
          <h4>SCORE SYSTEM:</h4>
          <div style="width: 100%; background: purple; min-height: 100px; padding: 20px; border-radius: 10px">
            <b-table-simple small responsive>
              <b-thead>
                <b-tr class="table-text">
                  <b-th colspan="1"><GiftIcon  size="1.5x"/> Score</b-th>
                  <b-th colspan="1"><CurrencyDollarIcon style="color: orange"  size="1.5x"/> Winning Platinum Reward</b-th>
                </b-tr>
              </b-thead>
              <b-tbody class="table-text">
                <b-tr v-for="item in data.score_system" :key="item.id">
                  <b-td>{{item.min}} - {{item.max}}</b-td>
                  <b-td>{{item.reward}} Platinum</b-td>
                </b-tr>
              </b-tbody>
            </b-table-simple>
          </div>
        </div>
          <div style="min-width: 40%">
            <h4>Rekomendasi Game lain:</h4>
            <div class="recomendation shadow">
              <b-img :src="data.thumbnail" fluid alt="Responsive image" style="border-radius: 10px"></b-img>
              <div class="flex" style="padding: 8px">
                <div>
                  <h6>GAME TITLE</h6>
                  <h6>MAX 2 ROW</h6>
                </div>
                <div>
                  <span style="font-size: 14px">Lorem ipsum</span>
                  <h6 style="color: orange"><CurrencyDollarIcon  size="1.5x"/>1.000<span style="font-size: 8px">Pt</span></h6>
                </div>
              </div>
            </div>  
            <div><a href="#" style="color: orangered; font-size: 24px; font-weight: 500;">LIHAT SEMUA GAME</a></div>
          </div>
        </div>
      </div>
    </b-container>
    <!-- footer -->
    <div class="footer">
      <div class="flex alignCenter gap24">
        <img alt="batgame logo" src="./assets/batgame.png" class="batgame">
        <span class="copyright">Copyright batgame.id ©. 2022 Rights Reserved</span>
      </div>
      <div class="flex gap24">
        <img alt="iso logo" src="./assets/iso.png" class="logo zoom">
        <img alt="kominfo logo" src="./assets/kominfo.png" class="logo">
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar/Navbar.vue'
import {  ShareIcon, CurrencyDollarIcon, GiftIcon } from '@vue-hero-icons/outline'
import datas from '@/assets/game-detail'

export default {
  name: 'App',
  data () {
    return {
      data: datas.data
    }
  },
  components: {
    Navbar,
    ShareIcon,
    CurrencyDollarIcon,
    GiftIcon
  },
  methods: {
    share: function () {
      console.log('share')
    },
    play: function () {
      console.log('play')
    },
    topUp: function () {
      console.log('topUp')
    },
    change: function () {
      console.log('tukar')
    },
  },
  computed: {}
}
</script>

<style scoped lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  min-height: 100vh;
  height: 100%;
  background-image: url('@/assets/purplebg.jpg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
.topBar {
  background-color: rgba(1, 0, 85, 0.8);
  color: white;
  width: 100%;
  padding: 10px;
}
.flex {
  justify-content: space-between;
  display: flex;
}
.alignCenter {
  align-items: center;
}
.gap {
  gap: 8px
}
.gap24 {
  gap: 24px
}
.content {
  background-color: rgba(1, 0, 85, 0.8);
  box-shadow: 0 0 5px 5px purple;
  border-radius: 8px;
  margin-top: 24px;
  color: white;
  padding: 24px;
}
.button {
  border-radius: 20px;
  background-color: purple;
  border: none;
}
.button:hover {
  background-color: purple;
  opacity: 0.8;
}
.btnOrange {
  border-radius: 20px;
  background-color: orange;
  border: none;
}
.btnOrange:hover {
  background-color: orange;
  opacity: 0.8;
}
.share {
  cursor: pointer
}
.title {
  font-size: 12px;
}
.shadow {
  box-shadow: 0 0 5px 5px purple;
}
.footer {
  background-color: rgb(21, 0, 43);
  justify-content: space-between;
  align-items: center;
  display: flex;
  padding: 20px;
  color: white;
}
.batgame {
  width: 150px;
}
.logo {
  height: 60px;
  width: 60px;
  overflow: hidden;
}
.zoom {
  transform: scale(1.2)
}
.media {
  min-width: 532px;
  width: 60%
}
.description {
  min-width: 330px;
}
.table-text {
  color: white;
}
.recomendation {
  background: rgb(4, 0, 66);
  border-radius: 10px;
  min-width: 210px;
  width: 60%;
}

@media only screen and (min-width: 2000px) {
  .footer {
    position: fixed;
    bottom: 0;
    width: 100%;
  }
}
@media only screen and (max-width:1000px) {
  .title {
    font-size: 10px;
  }
  .subtitle {
    font-size: 12px;
  }
  .flex {
    flex-wrap: wrap;
  }
  .media {
    min-width: 0;
    width: 100%
  }
  .description {
    min-width: 0;
  }
}
@media only screen and (max-width: 770px) {
  #topBarRight {
    display: none;
  }
  .logo {
    width: 30px;
    height: 30px;
  }
  .batgame {
    width: 100px
  }
  .copyright {
    font-size: 12px;
  }
}
@media only screen and (max-width: 500px) {
  .table-text {
    font-size: 10px;
  }
  .copyright {
    display: none
  }
}
</style>
