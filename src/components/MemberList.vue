<template>
    <div class="members">
        <div class="container">
            <h2 class="head-styled">Seznam členů</h2>
            <ul>
                <li v-for="member in members" v-bind:key="member">
                    <button>
                        <h3>
                            {{member.name}}
                        </h3>
                        <img class="logo" :src="member.logo" :alt="'logo '+member.name"> 
                    </button>
                </li>
            </ul>
        </div>
    </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

interface Member {
    name: string;
    logo: string;
    summary: string;
    description: string;
    contactPlace: string;
    contactEmail: string;
    images: string[];
}

export default class MemberList extends Vue {
    public members: Member[]=[
        {
            name:'twentio',
            logo: require('@/assets/twentio.svg'),
            summary:'',
            description:'',
            contactPlace:'',
            contactEmail:'',
            images:[],
        },
         {
            name:'twentio',
            logo: require('@/assets/logo.svg'),
            summary:'',
            description:'',
            contactPlace:'',
            contactEmail:'',
            images:[],
        },
         {
            name:'twentio',
            logo: require('@/assets/logo.svg'),
            summary:'',
            description:'',
            contactPlace:'',
            contactEmail:'',
            images:[],
        },
          {
            name:'twentio',
            logo: require('@/assets/logo.svg'),
            summary:'',
            description:'',
            contactPlace:'',
            contactEmail:'',
            images:[],
        },
    ]
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .members{
      margin: 2rem 0;
      .container{
          ul{
              width: 100%;
              position: relative;
              list-style: none;
              display: flex;
              align-items: center;
              flex-wrap: wrap;
              justify-content: space-between;
              li{
                  margin: 0.25rem;
                  width: calc( ( 100% / 3 ) - 0.5rem);
                  position: relative;
                  button{
                      width: 100%;
                      min-height: 300px;
                      background: #fff;
                      outline: none;
                      border-radius: 0;
                      border: none;
                      cursor: pointer;
                      border: 1px solid #000;
                      .logo{
                          width: 100px;
                      }
                  }
              }
          }
      }
  }
</style>