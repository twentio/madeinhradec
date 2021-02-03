<template>
  <nav v-bind:class="{ open: menu }">
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
        <li>
          <a href="https://twentio.cz/redact-x" target="_blank">systém</a>
        </li>
      </ul>
      <div class="operators">
        <button v-bind:class="{ close: menu }" @click="showDetail()">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Menu extends Vue {
  public menu = false;

  showDetail() {
    this.menu = !this.menu;
  }
}
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
    align-items: center;
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
      @media (max-width: 768px) {
        display: none;
      }

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
    .operators {
      display: flex;
      align-items: center;
      justify-content: center;
      @media (min-width: 768px) {
        display: none;
      }
      button {
        background: transparent;
        border-radius: 0;
        margin: 0;
        border: none;
        outline: none;
        cursor: pointer;
        width: 45px;
        height: 45px;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;

        span {
          display: block;
          width: 33px;
          height: 2px;
          margin-bottom: 0.5rem;
          position: relative;

          background: #212121;
          border-radius: 3px;

          z-index: 1;

          transform-origin: 4px 0px;

          transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1),
            background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), opacity 0.55s ease;
        }

        span:first-child {
          transform-origin: 0% 0%;
        }

        span:nth-last-child(2) {
          transform-origin: 0% 100%;
        }
        span:nth-child(3) {
          margin-bottom: 0;
        }

        &.close {
          span {
            opacity: 1;
            transform: rotate(-45deg) translate(4px, 0px);
            background: #232323;
          }

          span:nth-last-child(3) {
            opacity: 0;
            transform: rotate(0deg) scale(0.2, 0.2);
          }

          span:nth-last-child(2) {
            transform: rotate(45deg) translate(-6px, -13px);
          }
        }
      }
    }
  }
  &.open {
    .container {
      ul {
        display: flex;
        flex-direction: column;
        position: absolute;
        left: 0;
        width: 100%;
        top: calc(100% + 3px);
        height: 400px;
        background: #f7f7f7;
        li {
          height: 3rem;
          width: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
          text-align: center;
          &:first-child{
            margin-top: 1rem;
          }
          a {
            &:after {
              display: none;
            }
          }
        }
      }
    }
  }
}
</style>
