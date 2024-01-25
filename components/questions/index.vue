<template>
    <div class="questions tile--gray center-wrap flex --just-center tile" id="FAQ">
            <div class="questions__head">
                <div class="questions__title">How is the steaming procedure going?</div>
            </div>
        <div class="questions__container flex --just-space">
            <div class="questions__list grid">
                <div class="questions__list-col --left">
                    <div :class="{'is-open' : isOpen.includes(item.id)}" class="questions__item tile-min tile" v-for="(item, index) in questions.leftColQuestionsArr" :key="index">
                        <div  v-on:click="openMenu(item.id)" class="questions__item-clicker flex --just-space --align-center">
                            <div class="questions__item-text col --auto"  v-if="item.question" v-html="item.question"></div>
                            <div class="questions__item-btn"></div>
                        </div>
                        <div class="questions__item-dropdown" >
                            <div class="questions__item-dropdown-inner p --l" v-if="item.answer" v-html="item.answer">
                            </div>
                        </div>
                    </div>
                    <div :class="{'is-open' : isOpen.includes(item.id)}" class="questions__item tile-min tile" v-for="(item, index) in questions.rightColQuestionsArr" :key="index">
                        <div v-on:click="openMenu(item.id)" class="questions__item-clicker flex --just-space --align-center">
                            <div class="questions__item-text col --auto" v-if="item.question" v-html="item.question"></div>
                            <div class="questions__item-btn"></div>
                        </div>
                        <div class="questions__item-dropdown">
                            <div class="questions__item-dropdown-inner p --l" v-if="item.answer" v-html="item.answer"></div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="questions__preview col --6">
                <nuxt-picture
                    preload="true"
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
</template>

<script>
    export default {
        data() {
            return { 
                device: 'desktop',
                isOpen: [],
                questions: {
                    leftColQuestionsArr: [
                        {
                            id: 1,
                            question: 'Getting to know each other + warming up',
                            answer: 'The temperature in the Bath is just 122 F. We are sitting comfortably and warming up. We breathe the fresh frosty air from the open windows. We drink tea, get acquainted, and discuss what will happen.'
                        },
                        {   
                            id: 2,
                            question: 'The first steam',
                            answer: 'Mint-anise steam with juniper. Sprinkling and light steaming'
                        },
                        {   
                            id: 3,
                            question: 'Concentrated steam',
                            answer: 'Accentuated soaring of the legs with oak brooms. The contrast of the icy sheet and the cooling of the head with mint water. Active hot steaming with oak brooms. The contrast in the icy cold pluche is 8°C.'
                        },
                        {   
                            id: 4,
                            question: 'Rest on the couch. Tea. ',
                            answer: 'You will take a 15 minutes rest and even will try to have a nep '
                        },                
                        {   
                            id: 4,
                            question: 'Rest on the couch. Tea. ',
                            answer: 'You will take a 15 minutes rest and even will try to have a nep '
                        },                  
                        {   
                            id: 4,
                            question: 'Rest on the couch. Tea. ',
                            answer: 'You will take a 15 minutes rest and even will try to have a nep '
                        },               
                        {   
                            id: 5,
                            question: 'Broom steaming with juniper and reheating on a sharp steam with oak veniks',
                        },               
                        {   
                            id: 6,
                            question: 'Scrubs (optional)',
                            answer: 'Steam inhalation on baked potatoes with garlic and dill. Warming up with fans in wormwood steam.'
                        },            
                        {   
                            id: 7,
                            question: 'Farewell to tears',
                        },                      
                    ],
                }
            }
        },
        methods: { 
            openMenu(id) {
                const indexId = this.isOpen.indexOf(id);
                const dropdownsArr = document.querySelectorAll('.questions__item-dropdown');
                if (indexId !== -1) {
                    this.isOpen.splice(indexId, 1)
                    this.$gsap.to(dropdownsArr[id - 1], {height: 0});
                } else {
                    this.isOpen.push(id)
                    this.$gsap.set(dropdownsArr[id - 1], {height: 'auto'});
                    this.$gsap.from(dropdownsArr[id - 1], {height: 0});
                }
            },
            openPopup(popup) {
                this.$store.dispatch('popup', popup);
            },
        },
        async mounted() {
            this.device = window.innerWidth <= 991 ? 'mobile' : 'desktop';
        }
    }
</script>

<style>
    @import "@/components/questions/__questions.css";
</style>