<template>
  <!-- # works
        ================================================== -->
  <section id="works" class="s-works target-section">
    <div class="row">
      <div class="column xl-12">
        <div class="section-header" data-num="02">
          <h2 class="text-display-title">Selected Works.</h2>
        </div> <!-- end section-header -->
      </div>
    </div>

    <div class="row folio-entries">
      <page-work-entry :entry-number="1"
                     entry-title="White Knit Cap"
                     entry-cat="Frontend Design"
                     :img-href="g_white_turban"
                     :img-src="white_turban"
                     :img-srcset="(white_turban) + ' 1x, ' + (white_turban2x) + ' 2x'">
        <!-- <template #img>
          <img src="/src/images/folio/grayscale.jpg" srcset="/src/images/folio/grayscale.jpg 1x, /src/images/folio/grayscale@2x.jpg 2x" alt="">
        </template> -->
        Lorem ipsum dolor sit amet consectetur, adipisicing elit.
        Inventore ipsum iste soluta fugiat, impedit illum ducimus
        deleniti facilis ab, tempora non! Nisi, tempora provident.
        <a href="https://www.behance.net/">Project Link</a>.
      </page-work-entry>
      <page-work-entry :entry-number="2"
                     entry-title="WoodCraft"
                     entry-cat="Product Design"
                     :img-href="g_woodcraft"
                     :img-src="woodcraft"
                     :img-srcset="(woodcraft) + ' 1x, ' + (woodcraft2x) + ' 2x'">
        <!-- <template #img>
          <img src="/src/images/folio/grayscale.jpg" srcset="/src/images/folio/grayscale.jpg 1x, /src/images/folio/grayscale@2x.jpg 2x" alt="">
        </template> -->
        Lorem ipsum dolor sit amet consectetur, adipisicing elit.
        Inventore ipsum iste soluta fugiat, impedit illum ducimus
        deleniti facilis ab, tempora non! Nisi, tempora provident.
        <a href="https://www.behance.net/">Project Link</a>.
      </page-work-entry>
      <page-work-entry :entry-number="3"
                     entry-title="Caffeine & Tulips"
                     entry-cat="Brand Identity"
                     :img-href="g_caffeine_and_tulips"
                     :img-src="caffeine_and_tulips"
                     :img-srcset="(caffeine_and_tulips) + ' 1x, ' + (caffeine_and_tulips2x) + ' 2x'">
        <!-- <template #img>
          <img src="/src/images/folio/grayscale.jpg" srcset="/src/images/folio/grayscale.jpg 1x, /src/images/folio/grayscale@2x.jpg 2x" alt="">
        </template> -->
        Lorem ipsum dolor sit amet consectetur, adipisicing elit.
        Inventore ipsum iste soluta fugiat, impedit illum ducimus
        deleniti facilis ab, tempora non! Nisi, tempora provident.
        <a href="https://www.behance.net/">Project Link</a>.
      </page-work-entry>
      <page-work-entry :entry-number="4"
                     entry-title="Grayscale"
                     entry-cat="Product Design"
                     :img-href="g_grayscale"
                     :img-src="grayscale"
                     :img-srcset="(grayscale) + ' 1x, ' + (grayscale2x) + ' 2x'">
        <!-- <template #img>
          <img src="/src/images/folio/grayscale.jpg" srcset="/src/images/folio/grayscale.jpg 1x, /src/images/folio/grayscale@2x.jpg 2x" alt="">
        </template> -->
        Lorem ipsum dolor sit amet consectetur, adipisicing elit.
        Inventore ipsum iste soluta fugiat, impedit illum ducimus
        deleniti facilis ab, tempora non! Nisi, tempora provident.
        <a href="https://www.behance.net/">Project Link</a>.
      </page-work-entry>
      <page-work-entry :entry-number="5"
                     entry-title="The Lamp"
                     entry-cat="Brand Identity"
                     :img-href="g_lamp"
                     :img-src="lamp"
                     :img-srcset="(lamp) + ' 1x, ' + (lamp2x) + ' 2x'">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit.
        Inventore ipsum iste soluta fugiat, impedit illum ducimus
        deleniti facilis ab, tempora non! Nisi, tempora provident.
        <a href="https://www.behance.net/">Project Link</a>.
      </page-work-entry>
      <page-work-entry :entry-number="6"
                     entry-title="Tropical"
                     entry-cat="Frontend Design"
                     :img-href="g_tropical"
                     :img-src="tropical"
                     :img-srcset="(tropical) + ' 1x, ' + (tropical2x) + ' 2x'">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit.
        Inventore ipsum iste soluta fugiat, impedit illum ducimus
        deleniti facilis ab, tempora non! Nisi, tempora provident.
        <a href="https://www.behance.net/">Project Link</a>.
      </page-work-entry>
    </div> <!-- folio entries -->

    <div class="row s-testimonials">
      <div class="column xl-12">
        <h3 class="s-testimonials__header">Hear it from My Happy Clients</h3>
        <div class="swiper-container s-testimonials__slider">
          <div class="swiper-wrapper">
            <page-work-slide :img-src="user02" author="John Rockefeller" company="Standard Oil Co.">
              Molestiae incidunt consequatur quis ipsa autem nam sit enim magni. Voluptas tempore rem.
              Explicabo a quaerat sint autem dolore ducimus ut consequatur neque. Nisi dolores quaerat
              fuga rem nihil nostrum.
              Laudantium quia consequatur molestias.
            </page-work-slide>
            <page-work-slide :img-src="user03" author="Andrew Carnegie" company="Carnegie Steel Co.">
              Excepturi nam cupiditate culpa doloremque deleniti repellat. Veniam quos repellat voluptas
              animi adipisci.
              Nisi eaque consequatur. Voluptatem dignissimos ut ducimus accusantium perspiciatis.
              Quasi voluptas eius distinctio. Atque eos maxime.
            </page-work-slide>
            <page-work-slide :img-src="user01" author="John Morgan" company="JP Morgan & Co.">
              Repellat dignissimos libero. Qui sed at corrupti expedita voluptas odit. Nihil ea quia
              nesciunt. Ducimus aut sed ipsam.
              Autem eaque officia cum exercitationem sunt voluptatum accusamus. Quasi voluptas eius
              distinctio.
              Voluptatem dignissimos ut.
            </page-work-slide>
            <page-work-slide :img-src="user06" author="Henry Ford" company="Ford Motor Co.">
              Nunc interdum lacus sit amet orci. Vestibulum dapibus nunc ac augue. Fusce vel dui. In ac
              felis
              quis tortor malesuada pretium. Curabitur vestibulum aliquam leo. Qui sed at corrupti
              expedita voluptas odit.
              Nihil ea quia nesciunt. Ducimus aut sed ipsam.
            </page-work-slide>
          </div> <!-- end swiper-wrapper -->
          <div class="swiper-pagination"></div>
        </div> <!-- end swiper-container -->
      </div> <!-- end column -->
    </div> <!-- end s-testimonials -->
  </section> <!-- end s-works -->
</template>

<script setup>
import { onMounted } from 'vue';
import PageWorkEntry from './PageWorkEntry.vue';
import PageWorkSlide from './PageWorkSlide.vue';

import g_grayscale from "@/images/folio/gallery/g-grayscale.jpg";
import grayscale from "@/images/folio/grayscale.jpg";
import grayscale2x from "@/images/folio/grayscale@2x.jpg";

import g_tropical from "@/images/folio/gallery/g-tropical.jpg";
import tropical from "@/images/folio/tropical.jpg";
import tropical2x from "@/images/folio/tropical@2x.jpg";

import g_lamp from "@/images/folio/gallery/g-lamp.jpg";
import lamp from "@/images/folio/lamp.jpg";
import lamp2x from "@/images/folio/lamp@2x.jpg";

import g_white_turban from "@/images/folio/gallery/g-turban.jpg";
import white_turban from "@/images/folio/white_turban.jpg";
import white_turban2x from "@/images/folio/white_turban@2x.jpg";

import g_caffeine_and_tulips from "@/images/folio/gallery/g-tulips.jpg";
import caffeine_and_tulips from "@/images/folio/caffeine_and_tulips.jpg";
import caffeine_and_tulips2x from "@/images/folio/caffeine_and_tulips@2x.jpg";

import g_woodcraft from "@/images/folio/gallery/g-woodcraft.jpg";
import woodcraft from "@/images/folio/woodcraft.jpg";
import woodcraft2x from "@/images/folio/woodcraft@2x.jpg";

import user01 from "@/images/avatars/user-01.jpg";
import user02 from "@/images/avatars/user-02.jpg";
import user03 from "@/images/avatars/user-03.jpg";
import user06 from "@/images/avatars/user-06.jpg";

onMounted(() => {
  const ssSwiper = function () {
    const testimonialsSwiper = new Swiper('.swiper-container', {
      slidesPerView: 1,
      pagination: {
        el: '.swiper-pagination',
        clickable: true,
      },
      breakpoints: {
        // when window width is > 400px
        401: {
          slidesPerView: 1,
          spaceBetween: 20
        },
        // when window width is > 800px
        801: {
          slidesPerView: 2,
          spaceBetween: 50
        },
        // when window width is > 1180px
        1181: {
          slidesPerView: 3,
          spaceBetween: 48
        }
      }
    });
  }; // end ssSwiper
  ssSwiper()
})
</script>

<style lang="scss" scoped>
.s-works {
  padding-top: var(--vspace-6);
  padding-bottom: var(--vspace-1);

  .folio-entries {
    --width-grid-max: 1400px;
    margin-top: var(--vspace-0_5);
  }

  .s-testimonials {
    padding-top: var(--vspace-4_5);
    padding-bottom: var(--vspace-4);
    .s-testimonials__header {
      margin-top: 0;
      margin-bottom: var(--vspace-2);
      text-align: center;
    }

    .s-testimonials__slider {
      padding-bottom: var(--vspace-2);
    }
  }
}
</style>