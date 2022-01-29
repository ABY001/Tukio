<template>
  <div class="footer__div">
    <footer>
      <div class="container">
        <div class="left">
          <div class="col-1">
            <router-link class="header" :to="{ name: 'Home' }">
              <img
                :src="require(`../assets/img/EventslyColored.png`)"
                alt="Tukio_Logo"
                class="logo_img"
              />
            </router-link>
            <p class="footer">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor
            </p>
            <ul style="padding-top: 7px">
              <li>
                <a><twitter class="svg-icon" /></a>
              </li>
              <li>
                <a><instagram class="svg-icon" /></a>
              </li>
              <li>
                <a><email class="svg-icon" /></a>
              </li>
            </ul>
          </div>
          <div class="col-2" style="margin-right: 0px">
            <ul class="quick-links" style="margin: 0 auto">
              <p class="link-light link-title">Resources</p>
              <router-link class="link-light" :to="{ name: 'Home' }"
                >Features</router-link
              >
              <router-link class="link-light" :to="{ name: 'Hiring' }"
                >Login</router-link
              >
              <router-link class="link-light" :to="{ name: 'Contact' }"
                >Get Started</router-link
              >
            </ul>
          </div>
          <div class="col-2" style="margin-right: 0px">
            <ul class="quick-links" style="margin: 0 auto">
              <p class="link-light link-title">Services</p>
              <router-link class="link-light" :to="{ name: 'Home' }"
                >Features</router-link
              >
              <router-link class="link-light" :to="{ name: 'Hiring' }"
                >Login</router-link
              >
              <router-link class="link-light" :to="{ name: 'Contact' }"
                >Get Started</router-link
              >
              <router-link class="link-light" :to="{ name: 'Hiring' }"
                >Terms of Use</router-link
              >
              <router-link class="link-light" :to="{ name: 'Contact' }"
                >Privacy Policy</router-link
              >
            </ul>
          </div>
          <div class="col-2" style="margin-right: 0px">
            <ul class="quick-links" style="margin: 0 auto">
              <p class="link-light link-title">Links</p>
              <router-link class="link-light" :to="{ name: 'Home' }"
                >Features</router-link
              >
              <router-link class="link-light" :to="{ name: 'Hiring' }"
                >Login</router-link
              >
              <router-link class="link-light" :to="{ name: 'Contact' }"
                >Get Started</router-link
              >
              <router-link class="link-light" :to="{ name: 'Hiring' }"
                >Legal</router-link
              >
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>
 
<script>
import email from "../assets/img/email.svg";
import twitter from "../assets/img/twitter.svg";
import instagram from "../assets/img/instagram.svg";
export default {
  name: "footer-vue",
  components: {
    email,
    twitter,
    instagram,
  },
  computed: {},
};
</script>
 
<style lang="scss" scoped>
.footer-policy {
  height: var(--sub-footer-height);
  background-color: var(--primary-color);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100%;
  padding: 0.7rem 25px;
  color: var(--footer-color);
}

.footer__data {
  max-width: 968px;
  margin: 0 auto;
  padding-top: 1rem;
  padding-bottom: 1rem;
  padding-left: 2rem;
  padding-right: 2rem;
}

.footer__container {
  // padding: 0.7rem 25px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: var(--small-font-size);
  @media (max-width: 768px) {
    flex-direction: column;
  }
  .footer__content2 {
    color: white !important;
  }
}

.footer__content {
  justify-content: center;
}
.subcontainer {
  width: 100%;
  margin: 0;
}

.footer__div {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
}

footer {
  margin-top: 60px;
  padding: 40px 25px;
  background-color: var(--footer-color);
  // font-weight: var(--font-semi-bold);
  .container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 32px;
    @media (min-width: 800px) {
      // flex-direction: row;
      justify-content: space-between;
      align-items: center;
      gap: 0px;
    }

    // > div {
    //   display: flex;
    //   flex: 1;
    // }

    .left {
      gap: 45px;
      color: var(--white-color);
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      font-size: var(--footer-font-size);
      @media (min-width: 768px) {
        flex-direction: row;
        gap: 0;
      }
      // @media (max-width: 768px) {
      //   flex-direction: row;
      //   align-items: start;
      //   gap: 0;
      // }

      .header {
        text-align: center;
        font-size: 24px;
        color: var(--black-color);
        // margin-bottom: 16px;
        text-decoration: none;
        font-weight: 600;
        @media (min-width: 800px) {
          text-align: initial;
        }
        .logo_img {
          width: 100px;
          float: left;
          // @media (max-width: 768px) {
          //   width: 35%;
          // }
        }
      }
      ul {
        gap: 16px;
        list-style: none;
        display: flex;
      }
      ul.quick-links {
        gap: 10px;
        list-style: none;
        display: flex;
      }

      .col-1,
      .col-2 {
        gap: 20px;
        // margin-right: var(--mb-3);
        display: flex;
        flex: 1;
        @media (min-width: 768px) {
          gap: 10px;
          margin-right: var(--mb-3);
        }
      }

      .col-1 {
        flex-direction: column;

        h2 {
          text-align: center;
          @media (min-width: 800px) {
            text-align: initial;
          }
        }
        ul {
          margin-top: auto;
          justify-content: start;

          li {
            display: flex;
            align-items: center;
            .svg-icon {
              // width: 24px;
              height: auto;
              color: var(--white-color);
            }
          }
        }
      }

      .col-2 {
        ul {
          height: 100%;
          justify-content: center;
          flex-direction: column;
          flex-wrap: wrap;
          @media (min-width: 800px) {
            flex-direction: column;
          }
          .link-title {
            cursor: text;
            margin-bottom: var(--mb-1);
            font-weight: var(--font-bold);
            font-size: var(--footer-title-font-size);
            @media (max-width: 768px) {
              margin-bottom: var(--mb-2);
            }
          }
        }
      }
    }

    .right {
      gap: 32px;
      color: var(--black-color);
      align-items: center;
      flex-direction: column;
      @media (min-width: 800px) {
        align-items: center;
        justify-content: flex-end;
        gap: 0;
      }
    }

    p.footer {
      // margin-top: auto;
      color: var(--white-color);
    }
  }
}
</style>
 

