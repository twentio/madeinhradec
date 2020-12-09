<template>
<footer>
    <div class="container">
        <div>
            <p>
            MadeInHradec © {{ new Date().getFullYear() }}
            <br>
            Všechna práva vyhrazena
            </p>
        </div>
        <div class="copy">
            <p>
            Vytvořilo studio 
            </p>
            <a href="https://twentio.cz" target="_blank">
                twentio
            </a>
        </div>
    </div>
</footer>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Menu extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    footer{
        padding: 3rem 0;
        background:#212121;
   
        .container{
                  display: flex;
    align-items: center;
    justify-content: space-between;
    p{
                    font-family: monospace;
        color: #fff;
    }
            .copy{
                display: flex;
                align-items: center;
                p{
                    margin-right: 0.5rem;
                }
            a{
                text-decoration: none;
                color: #fff;
                display: flex;
                align-items: center;
                font-size: 1.5rem;
                line-height: 1;
                margin-bottom: 3px;
                font-family: myriad-pro,sans-serif;
                font-weight: 900;
                font-style: normal;
            }
        }
        }
    }
</style>