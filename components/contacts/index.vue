<template>
  <section class="contacts py-48">
    <div class="center-wrap contacts__container">
      <div class="contacts__head flex">
        <div class="section-title-wrap">
          <h2 class="section-title">Contacts</h2>
        </div>
      </div>

      <div class="contacts__socials socials mt-64">
        <div class="socials__list flex --direction-column --gap-32">
          <a href="https://www.facebook.com/banyaofsanya"  target="_blank" class="socials__item">
            <div class="socials__item-icon">
                <FbSvg/>
            </div>
            <div class="socials__item-title">Facebook</div>
          </a>
          <a href="https://www.youtube.com/@SshashkaKravchuk"  target="_blank" class="socials__item">
            <div class="socials__item-icon">
                <YouSvg/>
            </div>
            <div class="socials__item-title">YouTube</div>
          </a>
          <a href="https://wa.me/+79267030363?text=Hi, Sanya!"  target="_blank" class="socials__item">
            <div class="socials__item-icon">
                <WhaSvg/>
            </div>
            <div class="socials__item-title">WhatsApp</div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>


<script>
import FbSvg from '~/assets/img/svg/facebook.svg?inline'
import YouSvg from '~/assets/img/svg/youtube.svg?inline'
import WhaSvg from '~/assets/img/svg/whatsapp.svg?inline'
export default {
    components: {
        FbSvg,
        YouSvg,
        WhaSvg,
    }
};
</script>

<style src="~/components/contacts/__contacts.css" lang="css"></style>