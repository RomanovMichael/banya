<template>
  <header class="header">
    <div
      class="header__container center-wrap py-32 flex --align-center --just-space"
    >
      <div class="header__burger-wrap">
        <div
          :class="{ 'is-open': $store.state.menu.is_open == true }"
          class="header__burger-btn flex --just-center --align-center"
          @click="openMenu()"
        >
          <div class="burder-btn__wrap">
            <div class="burger-btn__line"></div>
            <div class="burger-btn__line"></div>
          </div>
        </div>
      </div>
      <nav class="header__nav">
        <ul class="header__nav-list flex --align-center --gap-24">
          <li class="header__nav-item">
            <a href="#" @click="scrollTo('what')"  class="header__nav-link">What is a Banya</a>
          </li>
          <li class="header__nav-item">
            <a href="#" @click="scrollTo('prices')" class="header__nav-link">Prices</a>
          </li>
          <li class="header__nav-item">
            <a href="#" @click="scrollTo('about')"  class="header__nav-link">About me</a>
          </li>
          <li class="header__nav-item">
            <a href="#" @click="scrollTo('mission')" class="header__nav-link">Mission</a>
          </li>
          <li class="header__nav-item">
            <a href="#" @click="scrollTo('road')" class="header__nav-link">Road</a>
          </li>
          <li class="header__nav-item">
            <a href="#" @click="scrollTo('contacts')" class="header__nav-link">Contacts</a>
          </li>
        </ul>
      </nav>
      <a href="#" @click="scrollTo('contacts')" class="header__logo flex --align-center --gap-8">
        <LogoSvg class="header__logo-icon" />
      </a>
      <a href="https://wa.me/+79267030363?text=Hi, Sanya!" target="_blank" class="header__order --desk btn">Appointment</a>
    </div>
    <transition
      v-on:before-enter="beforeEnter"
      v-on:enter="enter"
      v-on:leave="leave"
      v-bind:css="false"
    >
      <HeaderMenu v-show="$store.state.menu.is_open == true"></HeaderMenu>
    </transition>
  </header>
</template>

<script>
import LogoSvg from "~/assets/img/svg/logo.svg?inline";

export default {
  components: { LogoSvg },

  methods: {
    scrollTo(id) {
      let timeOut = this.$route.name !== this.path ? 500 : 50;

      setTimeout(() => {
        this.$gsap.to(window, { duration: 0.56, scrollTo: "#" + id });
      }, timeOut);

      document.querySelector("body").classList.remove("js-no-scroll");

      this.openMenu(false);
    },
    showOnScrollUp() {
      const gsap = this.$gsap;
      const header = document.querySelector(".header");

      const showAnimation = gsap
        .from(header, {
          yPercent: -200,
          paused: true,
          duration: 0.2,
        })
        .progress(1);

      this.$ScrollTrigger.create({
        start: function () {
          return `1px top`;
        },
        end: "max",
        // markers: true,
        onEnter: () => {
          setTimeout(() => {
            this.$store.dispatch("menuCssClass", "is-scroll");
          }, 200);
        },
        onLeaveBack: () => {
          this.$store.dispatch("menuCssClass", "");
        },
        onUpdate: (self) => {
          if (self.isActive) {
            if (self.direction == -1) {
              showAnimation.play();
              header.classList.add("is-scroll");
            } else {
              showAnimation.reverse();
              header.classList.remove("is-scroll");
            }
          } else {
            showAnimation.play();
            header.classList.add("is-scroll-end");
          }
        },
      });
    },

    openMenu: function (e) {
      this.$store.dispatch("menuToggle", e);
    },
    beforeEnter(el) {
      this.$gsap.set(el, {
        yPercent: 100,
      });
    },
    enter(el, done) {
      document.querySelector("body").classList.add("js-no-scroll");
      this.$gsap.to(el, {
        yPercent: 0,
        duration: 0.56,
        ease: "power4.out",
        onComplete: done,
      });
    },
    leave(el, done) {
      document.querySelector("body").classList.remove("js-no-scroll");

      this.$gsap.to(el, {
        yPercent: 100,
        duration: 0.56,
        ease: "power3.out",
        onComplete: done,
      });
    },
  },
  watch: {
    $route(to, from) {
      setTimeout(() => {
        this.path = to.name;
        document.querySelector("body").classList.remove("js-no-scroll");
        this.$store.dispatch("menuToggle", false);
      }, 1);
    },
  },
  async mounted() {
    this.$gsap.delayedCall(0.01, this.showOnScrollUp);
    console.log(this.$ScrollTrigger);
  },
};
</script>
<style src="~/components/header/__header.css" lang="css"></style>