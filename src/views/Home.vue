<template>
  <Menu />
  <div class="banner"></div>
  <Benefits />
  <div class="info">
    <h1>Stránka je aktuálně ve výstavbě</h1>
  </div>
  <Footer />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Menu from "@/components/Menu.vue"; // @ is an alias to /src
import Footer from "@/components/Footer.vue"; // @ is an alias to /src
import Benefits from "@/components/Benefits.vue"; // @ is an alias to /src

@Options({
  components: {
    Menu,
    Footer,
    Benefits,
  },
})
export default class Home extends Vue {}
</script>

<style lang="scss" scoped>
.info {
  width: 100%;
  height: 400px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}
.banner {
  background: url("../assets/images/bg.jpg");
  overflow: hidden;
  position: relative;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  margin: -2rem 0 2rem 0;
  width: 100%;
  height: 400px;
  &:after {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    background: url("../assets/images/grow-main.png");
    background-position: center;
    background-repeat: no-repeat;
    @media (min-width: 1536px) {
      background-size: 620px;
    }
    @media (max-width: 1536px) {
      background-size: 80%;
    }
    @media (max-width: 576px) {
      background-size: 95%;
    }
  }
}
</style>
