<template>
  <div class="modal-vue">
    <main class="l-main">
      <!-- overlay -->
      <div class="overlay" v-if="showModal" @click="showModal = false"></div>

      <!-- modal -->
      <div class="modal" v-if="showModal">
        <!-- <button class="close" @click="showModal = false">x</button> -->
        <span v-if="showForm">
          <div class="modal-head">
            <h3 class="success-text">
              Be one of the first to find your <br />
              <span style="color: #d8671b"> Crowd. </span>
            </h3>
            <span style="width: 120px">
              <img
                :src="require(`../assets/img/Eventsly.png`)"
                alt="Eventsly_Logo"
                class="modal_img"
              />
            </span>
          </div>
          <div class="modal-caption">
            We just need a few details to save your spot!
          </div>

          <div class="inputs">
            <div class="input">
              <input
                type="email"
                name="email"
                id="email"
                v-model="email"
                placeholder="Your email address"
              />
            </div>
            <div class="input">
              <input
                type="fullname"
                name="fullname"
                id="fullname"
                v-model="fullname"
                placeholder="Your full name"
              />
            </div>
            <div class="video get-started" style="margin-top: 5rem">
              <button class="start link" @click="register">
                Save Spot
              </button>
            </div>
          </div>
          <div class="footer-modal">
            <img
              :src="require(`../assets/img/modal-footer.png`)"
              alt=""
              style="height: 100%"
            />
          </div>
        </span>

        <span v-else>
          <div class="success-container">
            <success />
            <div class="success-text" style="margin: 13px auto">All Done!</div>
            <div class="success-content">
              Thank you for being a part of your journey. We’ll inform you about
              the product<br />
              launch soon.
            </div>
            <div class="get-started" style="margin-top: 4rem">
              <button class="start link" @click="showModal = false">
                Got it!
              </button>
            </div>
          </div>
        </span>
      </div>
      <section class="home ad-container" id="home" style="margin-top: 25px">
        <div class="section__container">
          <div class="home__box bg-white top-margin">
            <p class="home-head">
              Events bring people <span style="color: #d8671b">Together.</span>
            </p>
            <h3 class="home-title-center">
              There is no better way to bring people together! Stay up to date
              with the latest events happening around you.
            </h3>
            <div class="video get-started" style="margin-top: 40px">
              <button class="start link desktop" @click="showModal = true">
                Save Spot
              </button>
              <!-- <button class="start link mobile" @click="showModal = true">
                Get Started
              </button>
              <button class="start-light link mobile">Get The App</button> -->
            </div>
          </div>
          <div class="home__img">
            <img :src="require(`../assets/img/photo2.png`)" alt="" />
          </div>
        </div>
      </section>
      <section class="share bd-container section" id="about">
        <div class="title">
          <dash />
          <span style="margin-left: 1rem; font-weight: 500">
            About Eventsly
          </span>
        </div>
        <div class="create__container bd-grid">
          <div class="share__data">
            <p class="section-head">
              We understand the importance of human connection
            </p>
            <div class="section-content">
              We at Eventsly believe that humans can’t find true happiness and
              fufilment in isolation. In that vein, we’re on a one-track journey
              to finding you that person or group of persons that will bring
              some joy into your life!
            </div>
          </div>
          <div class="create__img">
            <img src="../assets/img/photo1.png" alt="" />
          </div>
        </div>

        <div class="create__container bd-grid">
          <div class="share__data" style="margin: auto">
            <p class="section-head">
              Why don’t you make some cash while having fun?
            </p>
            <div class="section-content">
              We also provide an avenue for everyone to sell online tickets for
              events hosted by you. So, if you feel an event is monetizable,
              monetize it!
            </div>
          </div>
          <div class="order__img">
            <img src="../assets/img/photo3.png" alt="" />
          </div>
        </div>

        <div class="create__container bd-grid" style="margin-bottom: 3rem">
          <div class="share__data">
            <p class="section-head">Share experiences with the ones you love</p>
            <div class="section-content">
              We provide easy ways to share these events with the people you
              want most by your side as we believe shared experiences is what
              life is all about.
            </div>
          </div>
          <div class="create__img">
            <img src="../assets/img/photo4.png" alt="" />
          </div>
        </div>
      </section>

      <section class="share bd-container section__alt" id="about">
        <div class="title">
          <dash />
          <span style="margin-left: 1rem; font-weight: 500">
            Save your spot
          </span>
        </div>
        <div class="explore__container">
          <div class="explore__title">
            We’re working on a product to deliver this to you ASAP!
          </div>
          <div class="explore__content">
            Save your spot with a pre-registered account by clicking the button
            below now!
          </div>
          <div class="get-started" style="margin-top: 40px">
            <router-link class="link" :to="{ name: 'Home' }"
              ><button class="start">Save Your Spot</button></router-link
            >
          </div>
        </div>
      </section>

      <section
        class="home cd-container section__alt"
        id="explore"
        style="margin-top: 25px"
      >
        <div class="section__container">
          <div class="step__box div__box">
            <div class="theater__img">
              Ready to find the next event?
              <!-- <img src="../assets/img/theater.png" class="theater" alt="" /> -->
            </div>
            <div class="started_title start">
              Get started in three easy steps
            </div>
            <div class="first_step">
              <one style="margin-right: 1.3rem" />Sign up with us
            </div>
            <div class="steps">
              <step style="margin: 0 2rem 0 0.8rem" />
              <span style="margin-top: 10px">
                We’ll keep your info safe, we promise. This will get you
                authenticated and ready to go.
              </span>
            </div>
            <div class="first_step">
              <two style="margin-right: 1.3rem" />Setup location
            </div>
            <div class="steps">
              <step style="margin: 0 2rem 0 0.8rem" />
              <span style="margin-top: 10px">
                We’ll also collect a rough estimate of your location to give you
                tailored social events!
              </span>
            </div>
            <div class="first_step">
              <three style="margin-right: 1.3rem" />Get access to thousands of
              events
            </div>
            <div class="get-started steps-button">
              <router-link class="link" :to="{ name: 'Home' }"
                ><button class="start-light">
                  Save Your Spot
                </button></router-link
              >
            </div>
          </div>
          <div class="home__img">
            <img :src="require(`../assets/img/photo6.png`)" alt="" />
          </div>
        </div>
      </section>

      <section class="share cd-container section__alt" id="about">
        <div class="title">
          <dash />
          <span style="margin-left: 1rem; font-weight: 500">
            Share Your Event!
          </span>
        </div>

        <div class="section__container" style="margin-top: 3rem">
          <div class="home__box div__box" style="text-align: initial">
            <p class="share-head">
              Do you want to promote your next
              <span style="color: #d8671b">event?</span>
            </p>
            <h3 class="home-title-start">
              This platform will also empower event planners in giving them the
              power to reach out to a wide range of audiences.
            </h3>
            <div class="video get-started" style="margin-top: 40px">
              <router-link class="link" :to="{ name: 'Home' }"
                ><button class="start">Save Your Spot</button></router-link
              >
            </div>
          </div>
          <div class="home__img mg-rt">
            <img
              :src="require(`../assets/img/photo5.png`)"
              alt=""
              class="desktop"
            />
            <img
              :src="require(`../assets/img/photo5-1.png`)"
              alt=""
              class="mobile"
            />
          </div>
        </div>
      </section>

      <section
        class="home cd-container section__alt mobile"
        id="home"
        style="margin-top: 25px"
      >
        <div class="section__container">
          <div class="step__box div__box">
            <div class="started_title">Download the free Tukio app</div>
            <div class="download__content">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. quat.
            </div>

            <div class="google-play">
              <img src="../assets/img/Google.png" width="150px" alt="" />
            </div>
            <!-- <div class="mobile-screen">
              <img src="../assets/img/phone.png" width="300px" alt="" />
            </div> -->
          </div>
        </div>
      </section>

      <section
        class="home cd-container section__alt mobile"
        id="home"
        style="margin-top: 25px; margin-bottom: 25px"
      >
        <div class="title">
          <dash />
          <span style="margin-left: 1rem; font-weight: 500"> FAQ’s </span>
        </div>
        <div class="section__container">
          <div class="step__box div__box">
            <div class="started_title" style="margin-top: 3rem">
              Frequently Asked Questions
            </div>
            <div class="download__content">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim
            </div>
          </div>
        </div>

        <div class="faq-container">
          <div class="card-wrapper">
            <div
              class="card-text-wrapper hide"
              id="faq"
              v-for="faq in faqs"
              :key="faq._id"
            >
              <arrowUp class="collapse__icon" id="minus" />
              <arrowDown class="expand__icon" id="plus" />
              <p class="card-title">
                {{ faq.question }}
              </p>
              <p class="card-text" id="text">
                {{ faq.answer }}
              </p>
            </div>
          </div>
        </div>

        <div class="get-started" style="margin-top: 40px">
          <router-link class="link" :to="{ name: 'Home' }"
            ><button class="start">Contact Us</button></router-link
          >
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import dash from "../assets/img/dash.svg";
import one from "../assets/img/01.svg";
import two from "../assets/img/02.svg";
import three from "../assets/img/03.svg";
import step from "../assets/img/step.svg";
import success from "../assets/img/success.svg";
import arrowDown from "../assets/icons/arrow-down.svg";
import arrowUp from "../assets/icons/arrow-up.svg";
import axios from "axios";
export default {
  name: "Home",
  components: { success, dash, one, two, three, step, arrowUp, arrowDown },
  created() {
    document.body.scrollTop = document.documentElement.scrollTop = 0;
  },
  data() {
    return {
      email: "",
      fullname: "",
      showModal: false,
      showForm: true,
      faqs: [
        {
          question: "How do i post an event",
          answer:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim",
        },
        {
          question: "How do i post an event",
          answer:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim",
        },
        {
          question: "How do i post an event",
          answer:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim",
        },
        {
          question: "How do i post an event",
          answer:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim",
        },
      ],
    };
  },
  mounted() {
    let answers = document.querySelectorAll(".card-text-wrapper");
    answers.forEach((event) => {
      event.addEventListener("click", () => {
        if (event.classList.contains("show")) {
          event.classList.remove("show");
          event.classList.add("hide");
        } else {
          event.classList.remove("hide");
          event.classList.add("show");
        }
      });
    });
  },
  methods: {
    test() {
      this.$tostini({
        message: "Delicious!",
        type: "success",
      });
    },
    async register() {
      if (this.email !== "" && this.fullname !== "") {
        this.error = false;
        this.errorMsg = "";

        var myHeaders = new Headers();
        myHeaders.append("Content-Type", "application/json");

        var raw = {
          email: this.email,
          fullname: this.fullname,
        };
        console.log("here", raw);

        axios
          .post(
            "https://eventsly-api.herokuapp.com/pre-register-api/v1/add-user/",
            raw
          )
          .then((response) => {
            console.log(response);
            if (response.status) {
              this.showForm = false;
            }
            // this.$router.push({ name: "Home" });
          })
          .then((result) => console.log(result))
          .catch((error) => console.log("error", error));
        return;
      }
      this.error = true;
      this.errorMsg = "Please fill out all the fields!";
      return;
    },
  },
};
</script>
<style lang="scss" scoped>
.home-wrapper {
  // display: flex;
  flex-direction: column;
  @media (min-width: 700px) {
    // min-height: 650px;
    // max-height: 650px;
    flex-direction: row;
  }
}

.mobile {
  display: none;
  text-align: center;
  @media (max-width: 700px) {
    display: block;
  }
  .partners {
    justify-content: center;
  }
}

.mobile {
  display: block;
  @media (min-width: 576px) {
    display: none;
  }
}

.desktop {
  display: block;
  @media (max-width: 576px) {
    display: none;
  }
}

.video {
  grid-template-columns: repeat(2, 200px);
  margin: 10px 10px 10px 0;
  align-items: center;
  gap: 0px;
  width: 100%;
  height: 100%;
  display: grid;
  @media (max-width: 576px) {
    gap: 20px;
    grid-template-columns: repeat(2, 1fr);
  }
  // @media (min-width: 768px) {
  //   gap: 25px;
  // }
  // @media (min-width: 968px) {
  //   gap: 30px;
  // }
  .video__box {
    // display: inline-block;
    font-size: var(--normal-font-size);
    font-weight: var(--font-weight-light);
    @media (max-width: 576px) {
      font-size: 0.838rem;
    }
  }
  .video__icon {
    // display: inline-block;
  }
}

.google-play,
.mobile-screen {
  text-align: center;
  margin: 8px auto 0px;
}

// .video {
//   grid-template-columns: repeat(2, 1fr);
//   align-items: center;
//   width: 100%;
//   height: 100%;
//   .video__box {
//     width: 100px;
//     height: 100%;
//     display: inline-block;
//     font-size: var(--normal-font-size);
//     font-weight: var(--font-weight-light);
//   }
// }

.first_step {
  font-weight: 500;
  font-size: 1.1rem;
  color: #d8671b;
}

.start {
  font-family: var(--header-font);
  font-weight: var(--font-light) !important;
}

.steps {
  display: flex;
}

.bg-white {
  background: rgba(255, 255, 255, 0.83);
  @media screen and (min-width: 576px) {
    padding: 3rem 12rem 3rem 5rem;
    margin-right: -9rem;
    z-index: 10;
  }
}

.started_title {
  font-weight: bold;
  font-size: 2rem;
  margin-bottom: 1.5rem;
  max-width: 300px;
  @media screen and (max-width: 576px) {
    margin: auto auto 1.5rem auto;
    text-align: center;
  }
}

.download__section {
  margin: 85px auto;
  @media (min-width: 576px) {
    margin: 85px auto;
  }
  @media (min-width: 768px) {
    margin: 100px auto;
  }
  @media (min-width: 968px) {
    margin: 120px auto;
  }
}

.get-working {
  text-align: center;
  margin: 170px auto;
  @media (max-width: 576px) {
    margin: 170px auto 120px auto;
  }
  button.start {
    width: 17rem;
    height: 4rem;
    font-size: var(--h3-font-size);
  }
}

.get-partner {
  text-align: center;
  margin: 50px auto;
  @media (max-width: 576px) {
    margin: 10px auto;
  }
  button.start {
    width: 17rem;
    height: 4rem;
    font-size: var(--h3-font-size);
  }
}

.get-going {
  text-align: start;
  margin: 50px auto;
  @media (max-width: 576px) {
    margin: 10px auto;
  }
  button.start {
    width: 17rem;
    height: 4rem;
    font-size: var(--h3-font-size);
    @media (max-width: 576px) {
      width: 13rem;
      height: 3.5rem;
    }
  }
}
.get-started {
  text-align: center;
  margin: 50px auto;
  @media (max-width: 576px) {
    margin: 10px auto;
  }
  button.start2 {
    width: 17rem;
    height: 4rem;
    font-size: var(--h3-font-size);
    @media (max-width: 576px) {
      width: 13rem;
      height: 3.5rem;
    }
  }
  button.start {
    background-color: var(--primary-color);
    color: var(--white-color);
    width: 12rem;
    height: 3.5rem;
    box-shadow: 0px 4px 4px rgba(255, 103, 0, 0.25);
    border-radius: 4px;
    font-size: var(--normal-font-size);
    @media (max-width: 576px) {
      width: 11rem;
      height: 3rem;
    }

    &:hover {
      background-color: var(--second-color);
    }
  }
  button.start-light {
    background-color: var(--white-color);
    color: var(--primary-color);
    border: 2px solid var(--primary-color);
    box-sizing: border-box;
    filter: drop-shadow(0px 4px 4px rgba(255, 103, 0, 0.22));
    width: 12rem;
    height: 3.5rem;
    font-size: var(--normal-font-size);
    @media (max-width: 576px) {
      width: 11rem;
      height: 3rem;
    }

    &:hover {
      background-color: var(--second-color);
    }
  }
}

.title {
  margin: 5rem auto 0.5rem;
  text-align: initial;
}

.ease-container {
  bottom: 0;
  // position: absolute;
}

.trusted-title {
  font-size: 1.6rem;
  color: var(--black-color);
  text-align: center;
  font-weight: var(--font-medium);
  //   margin-bottom: var(--mb-3);
  letter-spacing: 0.185em;
  @media (min-width: 576px) {
    letter-spacing: 0.185em;
    font-size: 1.6rem;
  }
  @media (min-width: 768px) {
    letter-spacing: 0.385em;
    font-size: 1.8rem;
  }
  @media (min-width: 968px) {
    letter-spacing: 0.685em;
    font-size: 2rem;
  }
}

.test {
  margin-top: var(--mb-3) auto;
}

.users__testimonial {
  //   margin-bottom: var(--mb-3);
  // margin: 70px;
  // padding: 5px 100px;

  text-align: center;
  font-weight: var(--font-bold);
  font-size: 2rem;
  align-items: center;
  justify-content: center;
  .desktop {
    color: var(--primary-color);
    display: flex;
    @media (max-width: 700px) {
      display: none;
    }
  }
  .mobile {
    color: var(--black-color);
    display: none;
    text-align: center;
    @media (max-width: 700px) {
      display: flex;
    }
  }
}
.bg-primary {
  background: var(--primary-color) no-repeat 95% 50%;
  border-radius: 0px 0px 0px 150px;
}
.section-card {
  min-height: 150px;
  background: #ffffff;
  border-radius: 30px;
  color: var(--primary-color);
  text-align: center;
  font-weight: var(--font-bold);
  font-size: 1.7rem;
  align-items: center;
  justify-content: center;
  position: relative;
  display: flex;
  flex-direction: column;
  max-width: 1050px;
  // margin: 40px auto;
  // margin-bottom: -160px;
  // height: 200px;
  // z-index: 1;
  @media (max-width: 768px) {
    max-width: 90%;
  }
  @media (max-width: 576px) {
    border-radius: 8px;
    // box-shadow: 3px 3px 7px 7px rgba(0, 0, 0, 0.25);
    margin: 40px 5px;
    padding: 15px 13px;
    max-width: 90%;
    // margin-bottom: 40px 5px -160px 40px;
    // z-index: 1;
  }
  @media (min-width: 576px) {
    margin: 50px;
    padding: 25px 55px;
    // padding: 25px 150px;
    // margin: 50px 50px -160px 50px;
    // z-index: 1;
  }
  @media (min-width: 768px) {
    margin: 60px;
    font-size: 1.8rem;
    padding: 40px 80px;

    // margin: 60px 60px -160px 60px;
    // font-size: 1.8rem;
    // padding: 40px 200px;
    // // margin-bottom: -160px;
    // z-index: 1;
  }
  @media (min-width: 968px) {
    margin: 70px;
    font-size: 2.5rem;
    padding: 50px 100px;

    // margin-bottom: -160px;
    // z-index: 1;
    // margin: 70px 70px -160px 70px;
    // font-size: 2.5rem;
    // padding: 50px 270px;
  }
}

.logistics__data {
  text-align: start;
  width: 60%;
  margin-right: 40%;
  padding-top: 1rem;
  padding-bottom: 1rem;
  padding-left: 2rem;
  padding-right: 2rem;
  @media (max-width: 768px) {
    width: 85%;
    margin-right: 15%;
  }
  @media (max-width: 968px) {
    width: 75%;
    margin-right: 25%;
  }
}
.delivery__data {
  text-align: end;
  width: 60%;
  margin-left: 40%;
  margin-right: 0;
  padding-top: 1rem;
  padding-bottom: 1rem;
  padding-left: 2rem;
  padding-right: 2rem;
  @media (max-width: 768px) {
    width: 85%;
    margin-left: 15%;
  }
  @media (max-width: 968px) {
    width: 75%;
    margin-left: 25%;
  }
}

.card-wrapper {
  width: 100%;
  margin-top: 3rem;
  position: relative;
  @media screen and (max-width: 768px) {
    margin-top: 2.5rem;
  }
}
.card-text {
  font-weight: var(--font-weight-medium);
  line-height: 27px;
  width: 80%;
  margin-top: 1rem;
  @media screen and (max-width: 768px) {
    width: 100%;
  }
}
.card-text-wrapper {
  // bottom: 0;
  // width: 100%;
  // padding: 3rem;
  // box-sizing: border-box;
  // // background-color: blue;

  margin: 2rem 0;
  background: rgba(255, 255, 255, 0.12);
  border: 3px solid #d8671b;
  box-sizing: border-box;
  border-radius: 7px;
  @media screen and (max-width: 768px) {
    padding: 1.5rem 2rem;
  }
  &.hide .collapse__icon {
    display: none;
  }
  &.hide .expand__icon {
    display: block;
  }
  &.hide .card-text {
    display: none;
  }
  &.show .collapse__icon {
    display: block;
  }
  &.show .expand__icon {
    display: none;
  }
  &.show .card-text {
    display: block;
  }
}
.card-title {
  font-size: 21px;
  line-height: 30px;
  font-weight: var(--font-medium);
  text-align: initial;
}
.expand__icon,
.collapse__icon {
  float: right;
  text-align: center;
  margin-top: 7px;
}

.logistics-head {
  color: var(--black-color);
  font-weight: var(--font-bold);
  font-size: var(--large-font-size);
}
.logistics-title-center {
  font-size: var(--h2-font-size);
  color: var(--black-color);
  margin: 30px auto;
  font-weight: var(--font-bold);
  @media (max-width: 576px) {
    margin: 10px auto;
  }
}
.delivery-head {
  color: var(--white-color);
  font-weight: var(--font-bold);
  font-size: var(--large-font-size);
}
.delivery-title-center {
  font-size: var(--h2-font-size);
  color: var(--white-color);
  margin: 30px auto;
  font-weight: var(--font-bold);
  @media (max-width: 576px) {
    margin: 10px auto;
  }
}
.home__img {
  justify-self: center;
  padding: 0;
  //   max-width: 500px;
  @media (max-width: 576px) {
    margin-top: 75px;
    padding: 0;
  }
  // img {
  //   // max-height: 800px;
  //   width: 100%;
  // }
}
.trust {
  margin-top: var(--mb-3);
  @media (max-width: 576px) {
    margin-top: var(--mb-1);
  }
}
.biz {
  margin-top: var(--mb-6);
  @media (max-width: 576px) {
    margin-top: var(--mb-3);
  }
}
.trusted {
  // display: flex;
  // align-items: center;
  text-align: center;
  gap: 20px;
  display: grid;
  grid-template-rows: 50px;
  grid-template-columns: repeat(6, 120px);
  align-items: center;
  justify-content: center;
  @media (max-width: 968px) {
    display: grid;
    gap: 20px;
    grid-template-rows: 50px;
    grid-template-columns: repeat(6, 90px);
  }
  @media (max-width: 576px) {
    display: grid;
    gap: 20px;
    grid-template-rows: 50px;
    grid-template-columns: repeat(3, 80px);
  }
  .svg-icon {
    // width: 8.125rem;
    // height: 2.5rem;
    margin: 1rem 1.5rem 1rem 0;
    color: var(--black-color);
  }
}
.trustee {
  display: flex;
  align-items: center;
  @media (max-width: 576px) {
    height: 100px;
  }
}
.partners {
  display: flex;
  align-items: center;
  .svg-icon {
    // width: 8.125rem;
    // height: 2.5rem;
    margin: 1rem 1rem 1rem 0;
    color: var(--black-color);
  }
}

.sub-bd-container {
  /* max-width: 968px; */
  width: 100%;
  margin: 0;
}

.hd-grid {
  text-align: end;
}
.footer__container {
  row-gap: 0.5rem;
  // padding: 8rem 0;
  @media screen and (min-width: 968px) {
    grid-template-columns: repeat(2, 1fr);
    align-items: center;
    // padding: 16rem 8rem;
  }
  @media screen and (max-width: 768px) {
    grid-template-columns: repeat(2, 1fr);
    align-items: center;
  }
}
.footer__container .color-overlay {
  padding: 8rem 0;
  @media screen and (min-width: 968px) {
    padding: 16rem 8rem;
  }
  @media screen and (max-width: 768px) {
    padding: 8rem 0;
  }
}

.containerr {
  width: 100%;
  height: 400px;
  position: relative;
  background: linear-gradient(180deg, #ff6600 0%, #dd5800 100%);
  border-radius: 0px 150px 0px 300px;
  background-position: -10%;
  @media (max-width: 680px) {
    height: 920px;
  }
  @media (min-width: 680px) and (max-width: 968px) {
    height: 332px;
  }
  // margin: 0;
}
.box {
  position: absolute;
  top: -155px;
  left: 0;
  right: 0;
  opacity: 1;
  box-shadow: 3.72794px 3.72794px 7.45587px rgba(0, 0, 0, 0.25);
  @media (max-width: 680px) {
    top: -112px;
  }
  @media (min-width: 680px) and (max-width: 968px) {
    top: -105px;
  }
}
// .overlay {
//   margin: 30px auto;
//   @media (max-width: 576px) {
//     margin: 30px 20px;
//   }
//   @media (max-width: 768px) {
//     margin: 30px 30px;
//   }
//   @media (max-width: 1024px) {
//     margin: 30px 40px;
//   }
// }
.card-box {
  position: absolute;
  bottom: -110px;
  left: 0;
  right: 0;
  opacity: 1;
  @media (max-width: 680px) {
    bottom: -152px;
  }
}
.footer-modal {
  position: absolute;
  height: 0px;
  bottom: 0;
  right: 0;
  @media (min-width: 576px) {
    height: 200px;
  }
}
.modal-caption {
  margin-top: 20px;
}
.modal-vue .overlay {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-vue .modal {
  position: relative;
  width: 80%;
  z-index: 9999;
  margin: 0 auto;
  padding: 30px;
  background-color: #fff;
  border-radius: 3px;
}

.modal-head {
  display: flex;
  justify-content: space-between;
}

.modal_img {
  width: 100%;
  margin-right: 0;
}

.modal-vue .close {
  position: absolute;
  top: 10px;
  right: 10px;
}

.inputs {
  width: 100%;
  max-width: 425px;
  background: #ffffff;
  padding-top: 40px;

  .error {
    color: red;
  }

  .input {
    // position: relative;
    // display: flex;
    // justify-content: center;
    // align-items: center;
    margin-bottom: 20px;

    input {
      width: 100%;
      background: #fdfaf9;
      border: 2px solid #d8671b;
      box-sizing: border-box;
      border-radius: 5px;
      height: 50px;
      padding: 4px 4px 4px 10px;

      &:focus {
        box-shadow: 0 0 28px #ff782e40;
      }
    }
  }
}

.success-container {
  margin: 20px;
  text-align: center;
}

.success-text {
  font-size: 2rem;
  line-height: 34px;
  font-weight: var(--font-semi-bold);
}

.success-content {
  font-weight: 600;
  font-size: 14px;
}

// .overlay {
//   margin: 30px auto;
// }
</style>
