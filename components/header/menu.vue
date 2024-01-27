<template>
    <div class="full-menu__wrap flex --align-center">
        <transition v-on:before-enter="beforeEnter" v-on:enter="enter" v-on:leave="leave" v-bind:css="false">
            <div v-show="($store.state.menu.is_open == true)" class="full-menu__side --span-6 flex --direction-column --just-space center-wrap">
                <div class="full-menu__section-wrap flex --align-center col  center-wrap" >
                    <transition v-on:before-enter="beforeEnterMenu" v-on:enter="enterMenu" v-on:leave="leaveMenu" v-bind:css="false">
                        <div class="center-wrap">
                            <div class="full-menu__section-link" @click="scrollTo('what')">What is a Banya</div>
                            <div class="full-menu__section-link" @click="scrollTo('Prices')">Prices</div>
                            <div class="full-menu__section-link" @click="scrollTo('about')">About me</div>
                            <div class="full-menu__section-link" @click="scrollTo('mission')">Mission</div>
                            <div class="full-menu__section-link" @click="scrollTo('road')">Road</div>
                            <div class="full-menu__section-link" @click="scrollTo('contacts')">Contacts</div>
                        </div>
                    </transition>
                </div>

            </div>
        </transition>
    </div>
</template>
<script>


    export default {
        data() {
            return {
                path: '',
                timeLineSplitText: null,
            }
        },
        components: {

        },
        computed: {
        },
        methods: {
            scrollTo(id){
                let timeOut = this.$route.name !== this.path ? 500 : 50;

                setTimeout(() => {
                    this.$gsap.to(window, {duration: .56, scrollTo: '#' + id});
                }, timeOut);

                document.querySelector('body').classList.remove('js-no-scroll');

                this.openMenu(false)
            },
            hideMenu(path){
                if (path === window.location.pathname) {
                    this.openMenu(false)
                }
            },
            scrollTo(id){
                let timeOut = this.$route.name !== this.path ? 500 : 50;

                setTimeout(() => {
                    this.$gsap.to(window, {duration: .56, scrollTo: '#' + id});
                }, timeOut);

                document.querySelector('body').classList.remove('js-no-scroll');

                this.openMenu(false)
            },
            openMenu: function (e) {
                this.$store.dispatch('menuToggle', e);
            },
            beforeEnterMenu(el) {
            },
            enterMenu(el, done) {

            },
            leaveMenu(el, done) {

            },
            beforeEnter(el) {
                this.$gsap.set(el, {
                    yPercent: 7,
                    opacity: 0,
                });
            },
            enter(el, done) {
                document.querySelector('body').classList.add('js-no-scroll');
                this.$gsap.to(el, {
                    yPercent: 0,
                    duration: 1,
                    delay: .32,
                    opacity: 1,
                    ease: "power4.out",
                    onComplete: done
                })
            },
            leave(el, done) {
                document.querySelector('body').classList.remove('js-no-scroll');
                this.$gsap.to(el, {
                    yPercent: 5,
                    duration: .56,
                    opacity: 0,
                    ease: "power3.out",
                    onComplete: done,
                })
            },
        },
        watch: {'$route' (to, from) {
            setTimeout(() => {
                console.log(to, from);

                this.path = to.name;
            }, 1);
        }}
    }
</script>

<style>
    @import "@/components/header/__fullmenu.css";
</style>
