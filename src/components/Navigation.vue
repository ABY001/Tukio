<template>
  <header>
    <nav class="container">
      <div class="branding">
        <router-link class="header" :to="{ name: 'Home' }">
          <img
            :src="require(`../assets/img/Eventsly.png`)"
            alt="Eventsly_Logo"
            class="logo_img"
          />
        </router-link>
      </div>
      <div class="nav-links">
        <ul v-show="!mobile">
          <a href="#home" class="link">Home</a>
          <a href="#about" class="link">About</a>
          <a href="#explore" class="link">Explore</a>
          <a href="#footer" class="link">Contact Us</a>
        </ul>
      </div>
    </nav>

    <menuIcon @click="toggleMobileNav" class="menu-icon" v-show="mobile" />
    <transition name="mobile-nav">
      <ul class="mobile-nav" v-show="mobileNav" @click="toggleMobileNav">
        <a href="#home" class="link">Home</a>
        <a href="#about" class="link">About</a>
        <a href="#explore" class="link">Explore</a>
        <a href="#footer" class="link">Contact Us</a>
      </ul>
    </transition>
  </header>
</template>

<script>
import menuIcon from "../assets/icons/hamburger.svg";
export default {
  name: "navigation",
  components: {
    menuIcon,
  },
  data() {
    return {
      profileMenu: null,
      mobile: null,
      mobileNav: null,
      windownWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
  },
  methods: {
    register() {},
    checkScreen() {
      this.windownWidth = window.innerWidth;
      if (this.windownWidth <= 750) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },

    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },

    toggleProfileMenu(e) {
      if (e.target === this.$refs.profile) {
        this.profileMenu = !this.profileMenu;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: calc(var(--header-height) + 20px);
  // line-height: 50px;
  @media (min-width: 900px) {
    height: calc(var(--header-height) + 40px + 1rem);
  }

  background-color: #fff;
  padding: 0 34px;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);
  z-index: 99;

  .link {
    padding: 0 8px;
    transition: 0.3s color ease;
    font-size: var(--normal-font-size);

    button {
      font-weight: var(--font-bold);
    }

    &:hover {
      color: var(--primary-color);
    }
  }

  nav {
    height: var(--header-height);
    display: flex;
    margin: 10px auto;
    @media (min-width: 900px) {
      margin: 20px auto;
      height: calc(var(--header-height) + 1rem);
    }

    // .logo_img {
    //   width: 60%;
    //   @media (min-width: 900px) {
    //     width: 90%;
    //   }
    // }

    .logo_img {
      margin-top: 18px;
      width: 80%;
      @media (max-width: 1200px) {
        width: 75%;
      }
      @media (max-width: 964px) {
        width: 60%;
      }
    }

    .branding {
      display: flex;
      align-items: center;
    }

    .nav-links {
      position: relative;
      display: flex;
      flex: 1;
      align-items: center;
      justify-content: flex-end;

      ul {
        margin-right: 0px;
        @media (max-width: 1200px) {
          margin-right: 22px;
        }
        @media (max-width: 964px) {
          margin-right: 12px;
        }

        .link {
          margin-right: 22px;
          @media (max-width: 1200px) {
            margin-right: 20px;
          }
          @media (max-width: 964px) {
            margin-right: 0px;
          }
        }

        .link:last-child {
          margin-right: 0;
        }
      }

      .profile {
        position: relative;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        color: #fff;
        background-color: #303030;

        span {
          pointer-events: none;
        }

        .profile-menu {
          position: absolute;
          top: 60px;
          right: 0;
          width: 250px;
          background-color: #303030;
          box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
            0 2px 4px -1px rgba(0, 0, 0, 0.06);

          .info {
            display: flex;
            align-items: center;
            padding: 15px;
            border-bottom: 1px solid #fff;

            .initials {
              position: initial;
              width: 40px;
              height: 40px;
              background-color: #fff;
              color: #303030;
              display: flex;
              align-items: center;
              justify-content: center;
              border-radius: 50%;
            }

            .right {
              flex: 1;
              margin-left: 24px;

              p:nth-child(1) {
                font-size: 14px;
              }

              p:nth-child(2),
              p:nth-child(3) {
                font-size: 12px;
              }
            }
          }

          .options {
            padding: 15px;
            .option {
              text-decoration: none;
              color: #fff;
              display: flex;
              align-items: center;
              margin-bottom: 12px;

              .icon {
                width: 18px;
                height: auto;
              }
              p {
                font-size: 14px;
                margin-left: 12px;
              }

              &:last-child {
                margin-bottom: 0px;
              }
            }
          }
        }
      }
    }

    .mobile-user-menu {
      margin-right: 40px;
    }
  }

  .menu-icon {
    cursor: pointer;
    position: absolute;
    top: 24px;
    right: 25px;
    height: 25px;
    width: auto;
  }

  .mobile-nav {
    padding: 20px;
    width: 70%;
    max-width: 250px;
    display: flex;
    flex-direction: column;
    position: fixed;
    height: 100%;
    background-color: #303030;
    top: 0;
    left: 0;

    .link {
      padding: 15px 0;
      color: #fff;
    }
  }

  .mobile-nav-enter-active,
  .mobile-nav-leave-active {
    transition: all 1s ease;
  }

  .mobile-nav-enter {
    transform: translateX(-250px);
  }

  .mobile-nav-enter-to {
    transform: translateX(0);
  }

  .mobile-nav-leave-to {
    transform: translateX(-250px);
  }
}
</style>
