<template>
    <section class="mission">
        <!-- <div class="mission__ps">
            *the design of this section is my personal idea not my web developer
        </div> -->
        <div class="mission__bg">
            <div class="missiom__bg-mask"></div>
            <nuxt-picture
            quality="100"
            class="lazy mission__image-thumb image-thumb"
            sizes="sm:641px, md:641px, lg:641px"
            format="webp"
            src="/mission/kits.jpeg"
            alt="Mission Banya of Sanya"
            />
        </div>
        <div class="mission__container center-wrap">
            <div class="mission__head flex">
                <div class="section-title-wrap">
                    <h2 class="section-title">Mission</h2>
                </div>
            </div>
            <div class="mission__content flex --align-center --gap-32">
                <div class="">
                    My mission revolves around creating a sustainable business model that enables single mothers worldwide to earn a daily 
                    income as steam masters in Banyas. 
                        <br><br>
                        Beginning in the USA and expanding to Ukraine and Russia, I aim to build a network of Banyas, accumulating profits and donations for further expansion.
                </div>
                <div class="">
                    Furthermore, I'm committed to addressing the psychological recovery needs of individuals affected by war. 
                        <br><br>
                        By utilizing Banyas as a platform for mental healing, I envision creating a PTSD recovery therapy program based on the therapeutic aspects of the Banya experience
                </div>
            </div>
        </div>
    </section>
</template>


<script>
export default {
    
}
</script>

<style src="~/components/mission/__mission.css" lang="css"></style>