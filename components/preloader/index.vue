<template>
  <div class="preloader flex --align-center --just-center">
    <div class="preloader__title-wrap">
      <!-- <div class="preloader__title">NATALEE ROMANOVA</div> -->
      <div class="preloader__subtitle">A Banya is a process of deep cleansing of the soul and body in combination with massage, aromatherapy and meditation.<br><br> This is the way to calm down, relax and purify.</div>
    </div>
    <!-- <div class="preloader__percents">
        <span id="percents">0</span> %
    </div> -->
    <div class="preloader__shade">
      <div class="preloader__bg">
          <nuxt-picture
            preload="true"
            quality="100"
            class="lazy hello__bg-thumb image-thumb"
            sizes="sm:641px, md:641px, lg:641px"
            format="webp"
            src="/preloader/prel.png"
            alt="Banya of Sanya background image"
          />
      </div>
    </div>
  </div>
</template>
<style>
@import "@/components/preloader/preloader.css";
</style>
<script>

export default {
  components: {
  },
  methods: {
    animationFadeIn(selector, delay) {
      const gsap = this.$gsap;
      gsap.from(selector, {
        delay: delay,
        // duration: 0.25,
        opacity: 0,
        ease: "power4.in-out",
      });
    },
    animationFadeOut(selector, delay) {
      const gsap = this.$gsap;
      gsap.to(selector, {
        delay: delay,
        duration: 0.5,
        opacity: 0,
        ease: "power4.out",
      });
    },
    fade() {
      this.$gsap.timeline().to(".preloader", {
        // delay: 100,
        delay: 3.25,
        yPercent: -100,
        ease: "power1.inOut",
        duration: 1.25,
      });

      setTimeout(() => {
        document.querySelector("body").classList.remove("js-no-scroll");
      }, 1600);
    },
    preloaderProgress() {
      const preloaderPercents = document.querySelector("#percents");
      const mediaFiles = document.querySelectorAll("img", "video");
      let i = 0;
      Array.from(mediaFiles).forEach((file, index) => {
        file.onload = () => {
          i++;
          preloaderPercents.innerHTML = ((i * 100) / mediaFiles.length);
        };
      });
    },
  },

  beforeMount() {
    document.querySelector("body").classList.add("js-no-scroll");
  },
  mounted() {
    // this.preloaderProgress();
    // this.fade();
  },
};
</script>