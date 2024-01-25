
<template>
    <section class="about" id="about">
        <div class="about__container center-wrap">
            <div class="about__title-wrap flex --just-center --mob">
                <h2 class="about__title">About me</h2>
            </div>
            <div class="about__content flex">
                <div class="about__text col --6">
                    <div class="about__text-head flex mb-56">
                        <div class="about__title-wrap  section-title-wrap --desk">
                            <h2 class="about__title section-title">About me</h2>
                        </div>
                    </div>
                    <p>My name is Sanya. </p>
                    <p> I'm from Crimea, I've been living in Moscow for the last few years. </p>
                    <p>After the war began, my friend Chris helped me, as a Ukrainian, with moving to the United States, where a year and a half later I decided to build a business in a Russian Bathhouse - Banya..</p>
                    <p>It doesn't sound politically correct to most people on the planet, but I don't give a fuck. I make the product I believe in.</p>
                </div>
                <div class="about__image col --6">
                    <nuxt-picture
                        quality="100"
                        class="lazy about__image-thumb image-thumb"
                        sizes="sm:641px, md:641px, lg:641px"
                        format="webp"
                        src="/about/about.png"
                        alt="About Banya of Sanya"
                    />
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    
}
</script>



<style src="~/components/about/__about.css" lang="css"></style>