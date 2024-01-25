<template>
  <div class="main">
      <!-- <Preloader :critical="true"/> -->
    <!-- <div class="main-mask__wrap">
      <div class="main-mask --mob">
        <nuxt-picture
          preload="true"
          quality="100"
          class="lazy hello__bg-thumb image-thumb"
          sizes="sm:641px, md:641px, lg:641px"
          format="webp"
          src="/preloader/bubles.png"
          alt="Banya of Sanya background image"
        />
      </div>
    </div> -->
    <Nuxt class="main-content" />
    <Popups />
  </div>
</template>

<script>
export default {}
</script>

