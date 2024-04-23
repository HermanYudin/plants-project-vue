<template>
  <div class="app" id="app">
    <header class="header">
      <headerMain />
    </header>
    <main class="main">
      <section class="home" id="Home">
        <div class="home-container">
          <Img :about="about" :imgHome="imgHome" :imgAbout="imgAbout" />
          <div class="disc-home-container">
            <DiscTitle
              :about="about"
              :titleHome="titleHome"
              :titleAbout="titleAbout"
            />
            <DiscText
              :about="about"
              :textAbout="textAbout"
              :textHome="textHome"
            />
            <a href="#About us"><Btn :prices="prices" /></a>
          </div>
        </div>
      </section>
      <section class="about" id="About us">
        <div class="home-container" :class="{ about: !about }">
          <Img :about="!about" :imgHome="imgHome" :imgAbout="imgAbout" />
          <div
            class="disc-home-container"
            :class="{ 'about-container': !about }"
          >
            <DiscTitle
              :about="!about"
              :titleHome="titleHome"
              :titleAbout="titleAbout"
            />
            <DiscText
              :about="!about"
              :textAbout="textAbout"
              :textHome="textHome"
            />
          </div>
        </div>
      </section>
      <section class="services" id="Service">
        <div class="services-container">
          <div class="services-nav-container">
            <TitleServices />
            <div class="btns-list-container">
              <BtnServ
                :btns="btns"
                @click="setActiveBtn(btn)"
                :activeBtns="activeBtns"
                :setActiveBtn="setActiveBtn"
                @set-btn="setActiveCard"
              />
            </div>
          </div>
          <div class="services-cards-container">
            <ServicesOneCard
              v-for="(card, index) in cards"
              :key="index"
              :card="card"
              :class="{ activeCards: activeCards.includes(card.category) }"
            />
          </div>
        </div>
      </section>
      <section class="prices">
        <pricesMain id="Price" />
      </section>
      <section class="contacts">
        <contactsMain id="Contacts" />
      </section>
    </main>
    <footer class="footer">
      <footerMain />
    </footer>
  </div>
</template>

<script>
import headerMain from "./components/header/headerMain";
import pricesMain from "./components/prices/pricesMain";
import contactsMain from "./components/contacts/contactsMain";
import footerMain from "./components/footer/footerMain";
import Img from "./components/home and about/Img.vue";
import DiscTitle from "./components/home and about/DiscTitle.vue";
import DiscText from "./components/home and about/DiscText";
import Btn from "./components/Btn";
import TitleServices from "../src/components/services/servicesNav/TitleServices.vue";
import BtnServ from "../src/components/services/servicesNav/BtnServ";
import ServicesOneCard from "../src/components/services/servicesCards/ServicesOneCard";

export default {
  name: "App",
  components: {
    headerMain,
    pricesMain,
    contactsMain,
    footerMain,
    Img,
    DiscTitle,
    DiscText,
    Btn,
    TitleServices,
    BtnServ,
    ServicesOneCard,
  },
  data() {
    return {
      about: false,
      prices: false,
      imgHome: require("/src/assets/svg/leafs.svg"),
      imgAbout: require("/src/assets/svg/houseplant 1.svg"),
      textHome:
        "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.",
      textAbout:
        "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.",
      titleHome: "We grow plants and give you oxygen",
      titleAbout: "We are professional experienced gardeners",
      btns: ["Garden", "Lawn", "Planting"],
      activeBtns: [],
      activeCards: "",
      cards: [
        {
          category: "Garden",
          img: require("/src/assets/images/1.jpg"),
          title: "Garden care",
          text: "Lorem Ipsum has been the industry 1",
        },
        {
          category: "Planting",
          img: require("/src/assets/images/2.jpg"),
          title: "Planting",
          text: "Lorem Ipsum has been the industry 2",
        },
        {
          category: "Lawn",
          img: require("/src/assets/images/3.jpg"),
          title: "Lawn care",
          text: "Lorem Ipsum has been the industry 3",
        },
        {
          category: "Planting",
          img: require("/src/assets/images/4.jpg"),
          title: "Planting",
          text: "Lorem Ipsum has been the industry 4",
        },
        {
          category: "Garden",
          img: require("/src/assets/images/5.jpg"),
          title: "Garden care",
          text: "Lorem Ipsum has been the industry 5",
        },
        {
          category: "Planting",
          img: require("/src/assets/images/6.jpg"),
          title: "Planting",
          text: "Lorem Ipsum has been the industry 6",
        },
      ],
    };
  },
  methods: {
    selectNavCard(value) {
      this.isSelected = value;
    },
    setActiveBtn(btn) {
      this.activeBtns.push(btn);
      if (this.activeBtns.length === 2) {
        this.activeBtns = [];
      }
    },
    setActiveCard(value) {
      this.activeCards = value;
    },
  },
};
</script>

<style scoped>
.header {
  background-color: #edf2ec;
}

.main {
  width: 100%;
  margin: 0 auto;
}

.home-container {
  background-color: #edf2ec;
  min-width: 1440px;
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.disc-home-container {
  margin: 65px 109px 93px auto;
  max-width: 549px;
  width: 100%;
}

.about {
  flex-direction: row-reverse;
}

.about-container {
  margin: 127px 109px 93px 110px;
}

.services-container {
  min-width: 1440px;
  width: 100%;
  background-color: #edf2ec;
}

.services-nav-container {
  display: flex;
  min-height: 94px;
  min-width: 1440px;
  width: 100%;
  padding-top: 24px;
  padding-left: 109px;
  padding-right: 324px;
  align-items: center;
}

.btns-list-container {
  display: flex;
  align-items: center;
  margin-left: 142px;
  gap: 34px;
}

.services-cards-container {
  padding-top: 47px;
  display: flex;
  flex-wrap: wrap;
  padding-bottom: 138px;
}

.activeCards {
  filter: blur(0px);
}
</style>
