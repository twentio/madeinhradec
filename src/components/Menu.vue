<template>
  <nav>
    <div class="container">
      <div class="logo">
        <router-link to="/">
          <img src="../assets/logo.svg" />
        </router-link>
      </div>
      <ul>
        <li>
          <router-link to="/">úvod</router-link>
        </li>
        <li>
          <router-link to="/o-nas">o nás</router-link>
        </li>
        <li>
          <router-link to="/clenove">členové</router-link>
        </li>
        <li class="eshop">
          <router-link to="/">eshop</router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Menu extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
nav {
  padding: 4px 0;
  /* position: absolute;
  top: 0;
  left: 0;*/
  margin-bottom: 2rem;
  width: 100%;
  height: 5rem;
  position: relative;
  z-index: 11;
  &::after {
    position: absolute;
    content: "";
    bottom: 0;
    left: 0;
    width: 100%;
    height: 1px;
    background: rgba(141, 148, 163, 0.16);
  }
  .container {
    height: 100%;
    position: relative;
    display: flex;
    justify-content: space-between;
    .logo {
      height: 100%;
      position: relative;
      display: flex;
      align-items: center;
      font-weight: bold;
      color: #fff;
      a {
        outline: none;
        padding: 8px;
        display: flex;
        align-items: center;
        &:focus {
          outline-style: dotted;
          outline-color: #212121;
        }

        img {
          width: 170px;
          height: 100%;
        }
      }
    }
    ul {
      height: 100%;
      position: relative;
      display: flex;
      justify-content: flex-start;
      align-items: center;
      li {
        height: 100%;
        align-items: center;
        display: flex;
        list-style: none;
        position: relative;
        a {
          cursor: pointer;
          height: 100%;
          padding: 0 0.75rem;
          color: #6e6e6e;
          position: relative;
          text-decoration: none;
          display: flex;
          align-items: center;
          outline: none;

          &:focus {
            outline-style: dotted;
            &:after {
              display: none !important;
            }
          }
          &.router-link-active {
            color: #212121;
            &:after {
              width: 32px;
              height: 1px;
              left: 50%;
              margin-left: -16px;
              bottom: -3px;
              position: absolute;
              display: block;
              content: "";
              background-color: #e10b0b;
            }
          }
          &:hover {
            color: #212121;
            &:after {
              width: 32px;
              height: 1px;
              left: 50%;
              margin-left: -16px;
              bottom: -3px;
              position: absolute;
              display: block;
              content: "";
              background-color: #e10b0b;
            }
          }
        }
      }
    }
  }
}
</style>
