<template>
  <Menu />
  <div class="info">
    <h1>Stránka je aktuálně ve výstavbě</h1>
  </div>
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
export default class Home extends Vue {}
</script>

<style lang="scss" scoped>
  .info{
    width: 100%;
    height: calc( 100vh - 80px - 32px - 126.4px ) ;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    
    }
</style>
