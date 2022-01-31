<template>
  <div class="app-wrapper">
    <div class="app">
      <Navigation v-if="!navigation" />
      <router-view class="top-margin" />
      <Footer v-if="!navigation" />
    </div>
  </div>
</template>

<script>
import Navigation from "./components/Navigation";
import Footer from "./components/Footer";
export default {
  name: "app",
  components: { Navigation, Footer },
  data() {
    return { navigation: null };
  },
  created() {
    this.checkRoute();
  },
  mounted() {},
  methods: {
    checkRoute() {
      if (this.$route.name === "Register") {
        this.navigation = true;
        return;
      }
      this.navigation = false;
    },
  },
  watch: {
    $route() {
      this.checkRoute();
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Raleway:wght@400;500;600;700&display=swap");
@import "./assets/styles/variables.css";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: var(--body-font);
}

.app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.link {
  cursor: pointer;
  text-decoration: none;
  font-weight: var(--font-semi-bold);
  color: var(--black-color);
}

.link-light {
  cursor: pointer;
  text-decoration: none;
  font-weight: var(--font-light);
  color: #fff;
}

.top-margin {
  margin-top: calc(var(--header-height) + 20px);
  @media (min-width: 900px) {
    margin-top: calc(var(--header-height) + 40px + 1rem);
  }
}

.blog-cards {
  display: grid;
  gap: 32px;
  grid-template-columns: 1fr;
  @media (min-width: 680px) {
    grid-template-columns: repeat(3, 1fr);
  }
  @media (min-width: 1200px) {
    grid-template-columns: repeat(3, 1fr);
  }
}

.slick-prev,
.slick-next {
  background: var(--primary-color) !important;
  border-radius: 15px;
  color: var(--primary-color) !important;
  @media (max-width: 576px) {
    background: var(--primary) !important;
    border-radius: 15px;
    color: var(--primary) !important;
  }
}
.slick-dots li.slick-active button:before {
  color: var(--primary-color) !important;
}

button,
.router-button {
  transition: 500ms ease all;
  cursor: pointer;
  // margin-top: 24px;
  padding: 12px 24px;
  background-color: var(--primary-color);
  color: var(--white-color);
  border-radius: 4px;
  border: none;
  font-weight: var(--font-bold);

  // text-transform: uppercase;

  &:focus {
    outline: none;
  }

  &:hover {
    background-color: #ff660094;
  }
}

.container {
  max-width: 1280px;
  margin: 0 auto;
}

.bd-container {
  max-width: 1140px;
  width: calc(100% - 3rem);
  margin-left: var(--mb-3);
  margin-right: var(--mb-3);
  @media screen and (min-width: 968px) {
    margin: 0.5rem auto;
  }
}

.faq-container {
  margin-left: auto;
  margin-right: auto;
}

.cd-container {
  // max-width: 1140px;
  // width: calc(100% - 3rem);
  margin-left: var(--mb-3);
  margin-right: var(--mb-3);
  @media screen and (min-width: 968px) {
    margin: 0.5rem 0 0.5rem 3rem;
  }
}

.mg-rt {
  @media (max-width: 576px) {
    margin-right: -3rem;
  }
}

.ad-container {
  width: 100%;
  margin: auto 0;
  @media screen and (max-width: 576px) {
    width: calc(100% - 3rem);
    margin-left: var(--mb-3);
    margin-right: var(--mb-3);
  }
}

.pp-container {
  max-width: 1000px;
  width: calc(100% - 3rem);
  margin: var(--mb-6) var(--mb-3) 0px;
  padding-top: var(--mb-3);
  @media screen and (min-width: 968px) {
    margin-left: auto;
    margin-right: auto;
  }
}

.sub-bd-container {
  width: 100%;
  margin: 0;
}

.create__container {
  row-gap: 0.5rem;
  margin: 3rem 0;
  @media screen and (min-width: 576px) {
    margin: 5rem 0;
    grid-template-columns: repeat(2, 1fr);
    align-items: center;
  }
  @media screen and (min-width: 968px) {
    column-gap: 5rem;
  }
  @media screen and (min-width: 768px) {
    .create__container {
      padding: 0 2rem;
    }
  }
}

/*========== CLASS CSS ==========*/
.section {
  padding: 4rem 0 2rem;
  @media screen and (min-width: 768px) {
    padding-top: 7rem;
  }
}

.section__alt {
  padding: 1rem 0;
  @media screen and (min-width: 768px) {
    padding: 2rem 0;
  }
}

.section-head {
  font-size: var(--h3-font-size);
  color: var(--title-color);
  font-weight: var(--font-semi-bold);
  margin-bottom: var(--mb-2);
}

.section-title {
  font-size: var(--h2-font-size);
  color: var(--title-color);
  text-align: center;
  //   margin-bottom: var(--mb-3);
}

.section-title-center {
  font-size: var(--h3-font-size);
  color: var(--black-color);
  text-align: center;
}

.explore__container {
  max-width: 500px;
  margin: auto;
}

.explore__content {
  text-align: center;
  margin: 5px auto;
}

.download__content {
  text-align: center;
  margin: 25px auto;
}

.explore__title {
  text-align: center;
  font-weight: 600;
  margin: 15px auto;
  font-size: 1.5rem;
}
/*========== LAYOUT ==========*/
.l-main {
  overflow: hidden;
}

.bd-grid {
  display: grid;
  gap: 3rem;
  @media (min-width: 576px) {
    gap: 2rem;
  }
}

.cd-grid {
  margin-top: 3rem;
  @media (min-width: 576px) {
    margin-top: 2rem;
  }
}

.create__img {
  max-width: 500px;
  align-content: flex-end;
}

.theater {
  background: #c4c4c4;
  border-radius: 23px;
}

.theater__img {
  margin: 10px auto 60px;
  background-image: url("assets/img/theater.png");
  color: white;
  border-radius: 23px;
  background-repeat: no-repeat;
  background-size: cover;
  height: 200px;
  font-weight: bold;
  font-size: 2rem;
  padding: 1rem 2rem;
  text-align: center;
  display: flex;
  align-items: center;
  @media (min-width: 576px) {
    display: none;
  }
}

.order__img {
  @media (min-width: 576px) {
    order: -1;
  }
  max-width: 500px;
  align-content: flex-start;
}

.steps-button {
  margin-top: 40px !important;
  text-align: start;
  @media (max-width: 576px) {
    text-align: center;
  }
}

.home-title-start,
.home-title-center {
  color: var(--black-color);
  font-weight: var(--font-light);
  font-size: var(--normal-font-size);
  @media (max-width: 576px) {
    font-size: 0.9rem;
  }
}

.home__box,
.home-title-center,
.video__box {
  text-align: initial;
  @media (max-width: 576px) {
    text-align: center;
  }
}

.step__box {
  text-align: initial;
}

.div__box {
  max-width: 500px;
}

.home-head {
  color: var(--black-color);
  font-weight: var(--font-bold);
  font-size: var(--biggest-font-size);
  line-height: 1.2;
  margin-bottom: var(--mb-2);
}

.share-head {
  color: var(--black-color);
  font-weight: var(--font-bold);
  font-size: var(--h2-font-size);
  line-height: 1.2;
  margin-bottom: var(--mb-2);
}

.share__data {
  text-align: center;
  @media screen and (min-width: 576px) {
    text-align: initial;
    max-width: 400px;
  }
}

.socials__icon {
  width: 9.7rem;
  // height: 3rem;
  margin: 1rem 1rem 1rem 0;
  padding: 2px 2px 2px 0;
  // border-radius: 0.6rem;
  opacity: 1;
  background-color: white !important;
  border-color: transparent !important;
  image-rendering: -webkit-optimize-contrast;
  @media (max-width: 576px) {
    width: 7.6rem;
    margin: 0.5rem 0.5rem 0.5rem 0;
  }
}

.partners__icon {
  width: 8.7rem;
  // height: 3rem;
  margin: 1rem;
  padding: 2px 2px 2px 0;
  // border-radius: 0.6rem;
  opacity: 1;
  background-color: white !important;
  border-color: transparent !important;
  image-rendering: -webkit-optimize-contrast;
  @media (max-width: 576px) {
    width: 6.6rem;
    margin: 0.5rem 0.5rem 0.5rem 0;
  }
}

.partner__icon {
  margin: 1rem;
  @media (max-width: 968px) {
    margin: 0.7rem;
  }
  @media (max-width: 576px) {
    margin: 0.5rem;
  }
}

.section__container {
  row-gap: 0.5rem;
  margin: 0;
  @media screen and (min-width: 968px) {
    // column-gap: 5rem;
  }
  @media screen and (min-width: 768px) {
    // padding: 0 2rem;
    margin: 0;
    display: grid;
  }
  @media screen and (min-width: 576px) {
    grid-template-columns: 50% 50%;
    align-items: center;
  }
}

/*========== FOOTERR ==========*/
.ft__background {
  background-color: var(--primary-color);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100%;
}

.footerr__title {
  font-size: var(--h3-font-size);
  color: var(--header-color);
  font-weight: var(--font-light);
  margin-bottom: var(--mb-2);
}

.footerr__description {
  margin-bottom: var(--mb-3);
  color: var(--header-color);
  font-size: var(--biggest-font-size);
  font-weight: var(--font-bold);
}

.footerr {
  height: var(--footer-height);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footerr__data {
  max-width: 968px;
  margin: 0 auto;
  padding-top: 2rem;
  padding-bottom: 2rem;
  padding-left: 2rem;
  padding-right: 2rem;
  @media screen and (max-width: 768px) {
    padding-left: 0;
    padding-right: 0;
  }
}

.footerr__container {
  row-gap: 0.5rem;
}

.fstore__icon {
  width: 10.5rem;
  height: 3.2rem;
  margin: 0.5rem;
  border-radius: 0.7rem;
  opacity: 1;
  background-color: white !important;
  border-color: transparent !important;
  image-rendering: -webkit-optimize-contrast;
  @media screen and (max-width: 768px) {
    width: 7.125rem;
    height: 2.5rem;
    margin: 0.5rem;
    border-radius: 0.6rem;
  }
  @media (min-width: 900px) {
    width: 13rem;
    height: 4rem;
    margin: 0.5rem;
    border-radius: 0.8rem;
  }
}

.hd-grid {
  text-align: center;
}
</style>
