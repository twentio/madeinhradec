<template>
  <Menu />
  <h1>Členové</h1>
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
export default class Members extends Vue {}
</script>
