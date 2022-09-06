<template>
  <div>
  <b-navbar toggleable="lg" type="dark" style="color: white;" class="bg">
    <b-container fluid="sm">
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#" @click="select = 'home'" :class="yellow('home')"><HomeIcon size="1x" /> Beranda</b-nav-item>
        <b-nav-item href="#" @click="select = 'game'" :class="yellow('game')"><ColorSwatchIcon size="1x"/> Game</b-nav-item>
        <b-nav-item href="#" @click="select = 'help'" :class="yellow('help')"><InformationCircleIcon size="1x"/> Bantuan</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-container>
  </b-navbar>
</div>
</template>

<script>
import { HomeIcon, ColorSwatchIcon, InformationCircleIcon } from "@vue-hero-icons/outline"

export default {
  name: 'Navbar',
  data () {
    return {
      select: 'home',
    }
  },
  components: {
    HomeIcon,
    ColorSwatchIcon,
    InformationCircleIcon
  },
  methods: {
    yellow: function(input) {
      return this.select == input ? 'selected' : ''
    }
  },
  computed: {},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .bg {
    background: rgba(85, 0, 71, 0.9);
  }
  .nav-link {
    align-items: center;
    display: flex;
    gap: 4px;
  }
  .navbar-dark {
    --bs-navbar-color: white;
  }
  .selected {
    border-bottom: 1px solid white;
  }
</style>
