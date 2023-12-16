<template>
  <!-- # about
        ================================================== -->
  <section id="about" class="s-about target-section">
    <div class="row s-about__content">
      <div class="column xl-12">
        <div class="section-header" data-num="01">
          <h2 class="text-display-title">About Me.</h2>
        </div> <!-- end section-header -->
        <p class="attention-getter">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptas explicabo id debitis cupiditate
          cumque, error quia! Debitis cupiditate ipsa nihil labore, earum atque dolor quos saepe vero inventore,
          odit nam deleniti accusantium omnis mollitia consequatur harum incidunt! Ex modi aut repudiandae
          doloremque commodi recusandae labore sit. Perspiciatis omnis dolor dolores fuga iusto, recusandae animi
          nisi consequuntur exercitationem id maxime earum pariatur voluptas! Porro non quos quae tempora fuga
          quis sequi minus sed sint debitis reiciendis, nostrum natus suscipit iusto odio.
        </p>

        <p class="attention-getter">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
          dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip
          ex ea commodo consequat. Duis aute irure dolor in reprehenderit. Ut enim ad minim
        </p>

        <div class="grid-list-items s-about__blocks">
          <page-about-block title="Experience" :list="experienceList" />
          <page-about-block title="Awards" :list="awardsList" />
          <page-about-block title="Skills" :list="skillsList" />
        </div> <!-- grid-list-items -->
      </div> <!--end column -->
    </div> <!--end s-about__content -->
  </section> <!-- end s-about -->
</template>

<script setup>
import { ref } from 'vue'
import PageAboutBlock from './PageAboutBlock.vue';

const experienceList = ref([{ name: "Spotify", desc: "Product Designer" },
                            { name: "Dropbox", desc: "Interface Developer" },
                            { name: "Google", desc: "Lead UI Designer" },
                            { name: "Figma", desc: "UI Designer" },
                            { name: "Microsoft", desc: "UI Designer" }])

const awardsList = ref([{ link: "#0", name: "Site Of The Month", desc: "Awwwards — 2023" },
                        { link: "#0", name: "Site Of The Day", desc: "Awwwards — 2023" },
                        { link: "#0", name: "Agency of The Year", desc: "Awwwards — 2022" },
                        { link: "#0", name: "FWA of The Month", desc: "FWA — 2022" },
                        { link: "#0", name: "Site Of The Month", desc: "Awwwards — 2022" }])

const skillsList = ref([{ name: "Product Design" },
                        { name: "UI/UX Design" },
                        { name: "Prototyping" },
                        { name: "Frontend Development" },
                        { name: "Illustration" },
                        { name: "Visual Design" }])
</script>

<style lang="scss" scoped>
.s-about {
  padding-top: var(--vspace-7);
  color: var(--color-3);

  .s-about__content {
    .s-about__blocks {
      margin-top: var(--vspace-3);
    }
  }
}

@media screen and (max-width: 800px) {
  .s-about {
    padding-top: var(--vspace-5);
  }
}
</style>