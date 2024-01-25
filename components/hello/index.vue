<template>
  <section class="hello">
    <div class="hello__bg">
      <div class="hello__bg-mask"></div>
      <video
        class="hello__bg-video"
        autoplay
        muted
        loop="true"
        src="/pr.mp4"
        type="video/mp4"
      ></video>
      <nuxt-picture
        quality="100"
        class="lazy hello__image-thumb image-thumb"
        sizes="sm:641px, md:641px, lg:641px"
        format="webp"
        src="/hello/hellobgmob.png"
        alt="About Banya of Sanya"
      />
    </div>
    <div class="hello__container center-wrap flex --align-center --just-center">
      <div class="hello__content pt-80">
        <div class="hello__text">
          <h1 class="hello__title --desk">
            Experience the Healthy High <br />
            Get Hooked, First Time's on me!
          </h1>
          <h1 class="hello__title --mob">
            Experience <br />
            the Healthy High<br />
            Get Hooked, <br />
            First Time's on me!
          </h1>
          <span class="hello__subtitle mt-32"> Banya of Sanya LLC </span>
        </div>
      </div>
      <div class="scrollDown">
        <i></i>
      </div>
    </div>
  </section>
</template>


<script>
export default {};
</script>

<style src="~/components/hello/__hello.css" lang="css"></style>