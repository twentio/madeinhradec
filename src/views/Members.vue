<template>
  <Menu />
  <div class="banner"></div>
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
<style lang="scss" scoped>
.banner {
  background: url("../assets/members-banner.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  margin: -2rem 0 2rem 0;
  width: 100%;
  height: 400px;
}
</style>
