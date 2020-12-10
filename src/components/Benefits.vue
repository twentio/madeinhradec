<template>
  <div class="benefits">
    <div class="container">
      <h2>Benefity</h2>
      <ul>
        <li>Propagace</li>
        <li>Technické zázemí</li>
        <li>Vytvoření vlastních stránek</li>
        <li>E-shop</li>
        <li>Rezervační systém</li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Benefits extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.benefits {
  margin-bottom: 2rem;
  h2{
    margin-bottom: 1rem;
  }
  ul {
    list-style: none;
    li {
      position: relative;
      height: 24px;
      padding-left: 1rem;
      &:before{
        content: "+";
        position: absolute;
        left: 0;
        top: 0;
        width: 1rem;
        height: 1rem;
      }
    }
  }
}
</style>