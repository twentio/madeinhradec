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
    Footer
  },
})
export default class About extends Vue {}
</script>
<style lang="scss" scoped>
.banner {
  background: url("../assets/about-banner.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  margin: -2rem 0 2rem 0;
  width: 100%;
  height: 400px;
}
</style>
