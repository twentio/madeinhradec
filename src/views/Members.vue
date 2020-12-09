<template>
  <Menu />
  <MemberList />
  <Footer />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Menu from "@/components/Menu.vue"; // @ is an alias to /src
import Footer from "@/components/Footer.vue"; // @ is an alias to /src
import MemberList from "@/components/MemberList.vue"; // @ is an alias to /src

@Options({
  components: {
    Menu,
    Footer,
    MemberList
  },
})
export default class Members extends Vue {}
</script>
