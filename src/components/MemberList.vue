<template>
  <div class="members">
    <div class="container">
      <h2 class="head-styled">Seznam členů</h2>
      <div class="content">
        <ul>
          <li v-for="(member, index) in members" v-bind:key="index">
            <button
              @click="
                showDetail();
                setDetail(index);
              "
            >
              <div class="content">
                <img
                  class="logo"
                  :src="member.logo"
                  :alt="'logo ' + member.name"
                />
                <h3>
                  {{ member.name }}
                </h3>
                <p>
                  {{ member.summary }}
                </p>
              </div>
            </button>
          </li>
        </ul>
        <div v-if="openDetail" class="detail">
          <div class="top">
            <div class="header">
              <div class="image">
                <img :src="detailMember.logo" />
              </div>
            </div>
            <div class="content-text">
              <h2>{{ detailMember.name }}</h2>
              <p>
                {{ detailMember.description }}
              </p>
              <a :href="detailMember.url" target="_blank">
                {{ detailMember.url }}
              </a>
              <p>
                {{ detailMember.contactPlace }}
              </p>
              <a v-for="phone in detailMember.contactPhone" v-bind:key="phone" :href="'tel:'+removeWhiteSpace(phone)"><br>
                {{ phone }}
              </a>
              <p v-for="email in detailMember.contactEmail" v-bind:key="email">
                {{ email }}
              </p>
              <p v-for="image in detailMember.images" v-bind:key="image">
                {{ image }}
              </p>
            </div>
          </div>
          <div class="images"></div>
          <button class="close" @click="showDetail()">
            <img src="../assets/close.svg" />
          </button>
        </div>
      </div>
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
  contactPhone: string[];
  contactEmail: string[];
  images: string[];
  url: string;
}

export default class MemberList extends Vue {
  public openDetail = false;
  public detailMember: Member;
  public members: Member[] = [
    {
      name: "Twentio s.r.o.",
      logo: require("@/assets/twentio.svg"),
      summary:
        "Děláme weby, aplikace a grafiku. Fotíme, točíme promo videa. Prostě všechno, co potřebujete pro svou online identitu.",
      description:
        "V roce 2018 se mladá parta studentů rozhodla vytvářet zprvu ze zábavy, poté komerčně webové stránky. Twentio znamená z překladu - twenty - stejně inovativní jako naši předchůdci ve 20. století. Na svém kontě už mají 3 roky praxe. Služby: Navrhování stránek, výroba e-shopů, redakčních systémů a podobných softwarových řešení.",
      contactPlace: "Hradecká 1151/9, Hradec Králové 500 03",
      contactPhone: ["+420 732 365 044", "+420 724 153 351"],
      contactEmail: [
        "jsme@twentio.cz",
        "kalousek@twentio.cz",
        "janik@twentio.cz",
      ],
      images: [],
      url: "https://twentio.cz",
    },
    {
      name: "Plenkylevne.cz",
      logo: require("@/assets/plenkylevne.svg"),
      summary:
        "Maloobchodní prodej potřeb pro děti.",
      description:
        "Nabízíme široký sortiment značkových plenek a dalšího sortimentu pro vaše nejmenší. Zboží máme skladem a odesíláme ho ihned, můžete ho mít tedy u sebe již druhý den.",
      contactPlace: "",
      contactPhone: ["+420 728 480 882"],
      contactEmail: [
        "info@plenkylevne.cz",
      ],
      images: [],
      url: "https://plenkylevne.cz",
    },
    {
      name: "itebo.cz",
      logo: require("@/assets/itebo.png"),
      summary:
        "Maloobchodní prodej drogerie.",
      description:
        "Potřebujete barvy, laky, kosmetiku nebo drogerii? Navštivte naši prodejnu v Hradci Králové. Nabízíme Vám barvy, laky, drogerii a kosmetiku v naší prodejně v Hradci Králové. V naší nabídce máme: - barvy Denas, Eternal, Remal, Het, Luxol - ředidla a rozpouštědla - peroxid 30% - kyselina solná - štětce a válečky - sádra a tmely - zakrývací folie a pásky - penetrace - dětské plenky DADA a NAPPY - pohlcovače vlhkosti a náplně - žárovky a baterie - prodlužovací kabely - teploměry - dioptrické čtecí brýle - potravinářské barvy - kosmetiku Bione cosmetics, Regina, Ryor, Bohemia cosmetics, Joanna BI-ES, Alpa a jiné. - česká drogerie Star, Cit, Savo, Real a jiné - houbičky, hadry, drátěnky - kbelíky Zboží je možno platit hotově nebo kartou.",
      contactPlace: "Pospíšilova 1155/33, 500 03 Hradec Králové",
      contactPhone: ["+420 728 480 882"],
      contactEmail: [
        "obchod@itebo.cz",
      ],
      images: [],
      url: "https://itebo.cz",
    },
      {
      name: "madeinhradec.cz",
      logo:  require("@/assets/logo.svg"),
      summary:
        "Chceme spojovat, poznávat a propagovat jednotlivé firmy a podnikatele v Hradci Králové. Zajímavé projekty pod značkou ‒ Made in Hradec.",
      description:
        "Chceme spojovat, poznávat a propagovat jednotlivé firmy a podnikatele v Hradci Králové. Zajímavé projekty pod značkou ‒ Made in Hradec.",
      contactPlace: "",
      contactPhone: ["+420 732 365 044"],
      contactEmail: [
        "jsme@twentio.cz",
      ],
      images: [],
      url: "https://twentio.cz",
    },
  ];
  setDetail(index: number) {
    this.detailMember = this.members[index];
  }
  showDetail() {
    this.openDetail = !this.openDetail;
  }
  removeWhiteSpace(data: string) {
      return data.replace(/ /g,'');
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.members {
  margin: 2rem 0;
  .container {
    .content {
      position: relative;
      ul {
        width: 100%;
        position: relative;
        list-style: none;
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        justify-content: space-between;
        li {
          margin-bottom: 0.75rem;
          width: calc((100% / 3) - 0.5rem);
          position: relative;
          button {
            width: 100%;
            min-height: 300px;
            background: #fff;
            outline: none;
            border-radius: 0;
            border: none;
            cursor: pointer;
            border: 1px solid #000;
            padding: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            .content {
              position: relative;
              display: flex;
              flex-direction: column;
              justify-content: center;
              align-items: center;
              p {
                width: 80%;
              }
              h3 {
                margin-bottom: 0.5rem;
              }
              .logo {
                margin-bottom: 1rem;
                width: 100px;
              }
            }
          }
        }
      }
      .detail {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: #fff;
        border: 1px solid #000;
        button {
          position: absolute;
          top: 16px;
          right: 16px;
          background: #fff;
          outline: none;
          border-radius: 0;
          border: none;
          cursor: pointer;
          padding: 0;
          width: 36px;
          height: 36px;

          img {
            width: 36px;
            height: 36px;
          }
        }
        .top {
          position: relative;
          display: flex;
          .header {
            width: 33%;
            max-width: 250px;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            padding: 1rem 0.5rem 0.5rem 1rem;
            .image {
              margin-top: 3rem;
              img {
                width: 150px;
              }
            }
          }
          .content-text {
            width: 77%;
            padding: 1rem 1rem 0.5rem 0.5rem;
            p {
              max-width: 600px;
            }
          }
        }
        .images {
        }
      }
    }
  }
}
</style>