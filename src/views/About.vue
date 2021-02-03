<template>
  <Menu />
  <div class="banner"></div>
  <h1>O nás</h1>
  <Footer />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Menu from "@/components/Menu.vue"; // @ is an alias to /src
import Footer from "@/components/Footer.vue"; // @ is an alias to /src

@Options({
  components: {
    Menu,
    Footer,
  },
})
export default class About extends Vue {}
</script>
<style lang="scss" scoped>
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
    background: url("../assets/images/how-it-started.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: calc(100% - 2rem);
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
