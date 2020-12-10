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
  background: url("../assets/grow-banner.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  margin: -2rem 0 2rem 0;
  width: 100%;
  height: 400px;
}
</style>
