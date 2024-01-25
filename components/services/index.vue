<template>
    <section class="services">
        <div class="services__container center-wrap">
            <div class="services__head flex --direction-column">
                <div class="section-title-wrap">
                    <h2 class="services__title section-title">
                        Prices
                    </h2>
                </div>
            </div>

            <div class="services__content grid --temp-col-3 --gap-24 mt-56">
                <div class="services__card">
                    <div class="services__card-head flex --gap-16">
                        <div class="services__card-icon --three"><ThreeSvg/></div>
                        <div class="services__card-title-wrap">
                            <div class="services__card-title">Three persons</div>
                        </div>
                    </div>
                    <div class="services__card-body">
                        <div class="services__card-price">
                               <div class="services__card-price-value-wrap"> 
                                    <div class="services__card-price-value">20$</div>
                               </div>
                            <div class="services__card-price-title">per hour</div>
                        </div>
                        <div class="services__card-image-wrap">
                            <div class="services__card-image">
                                <nuxt-picture
                                    quality="100"
                                    class="lazy services__card-image-thumb image-thumb"
                                    sizes="sm:641px, md:641px, lg:641px"
                                    format="webp"
                                    src="/prices/three.png"
                                    alt="About Banya of Sanya"
                                />
                            </div>
                        </div>
                        <div class="services__card-btn btn">Sign Up</div>
                    </div>
                </div>
                <div class="services__card">
                    <div class="services__card-head flex --gap-16">
                        <div class="services__card-icon --two"><TwoSvg/></div>
                        <div class="services__card-title-wrap">
                            <div class="services__card-title">Two persons</div>
                        </div>
                    </div>
                    <div class="services__card-body">
                        <div class="services__card-price">
                               <div class="services__card-price-value-wrap">
                                    <div class="services__card-price-value">25$</div>
                               </div>
                            <div class="services__card-price-title">per hour</div>
                        </div>
                        <div class="services__card-image-wrap">
                            <div class="services__card-image">
                                <nuxt-picture
                                    quality="100"
                                    class="lazy services__card-image-thumb image-thumb"
                                    sizes="sm:641px, md:641px, lg:641px"
                                    format="webp"
                                    src="/prices/two.png"
                                    alt="About Banya of Sanya"
                                />
                            </div>
                        </div>
                        <div class="services__card-btn btn">Sign Up</div>
                    </div>
                </div>
                <div class="services__card">
                    <div class="services__card-head flex --gap-16">
                        <div class="services__card-icon --one"><OneSvg/></div>
                        <div class="services__card-title-wrap">
                            <div class="services__card-title">One person</div>
                        </div>
                    </div>
                    <div class="services__card-body">
                        <div class="services__card-price">
                            <div class="services__card-price-value-wrap">
                                <div class="services__card-price-value">50$</div>
                            </div>
                            <div class="services__card-price-title">per hour</div>
                        </div>
                        <div class="services__card-image-wrap">
                            <div class="services__card-image --one">
                                <nuxt-picture
                                    quality="100"
                                    class="lazy services__card-image-thumb image-thumb"
                                    sizes="sm:641px, md:641px, lg:641px"
                                    format="webp"
                                    src="/prices/one.png"
                                    alt="About Banya of Sanya"
                                />
                            </div>
                        </div>
                        <div class="services__card-btn btn">Sign Up</div>

                    </div>
                </div>
            </div>
        </div>    
    </section>    
</template>


<script>

import OneSvg from "~/assets/img/prices/one.svg?inline";
import TwoSvg from "~/assets/img/prices/two.svg?inline";
import ThreeSvg from "~/assets/img/prices/three.svg?inline";
export default {
    components: {OneSvg,TwoSvg,ThreeSvg },
    data() {
        return {

        }
    }
}
</script>


<style src="~/components/services/__services.css" lang="css"></style>

