<template>
  <div class="grid-list-items__item s-about__block">
    <h4 class="s-about__block-title">{{ title }}</h4>
    <ul class="s-about__list">
      <li v-for="item of list">
        <template v-if="item.link">
          <a :href="item.link">
            {{ item.name }}
            <span>{{ item.desc }}</span>
          </a>
        </template>
        <template v-else>
          {{ item.name }}
          <span>{{ item.desc }}</span>
        </template>
      </li>
    </ul>
  </div> <!--end s-about__block -->
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  list: {
    type: Array,
    required: true,
  },
})
</script>

<style lang="scss" scoped>
.s-about__block {
  .s-about__block-title {
    margin-top: 0;
    margin-bottom: var(--vspace-1);
    padding-left: 1.45rem;
    position: relative;
  }

  .s-about__block-title::before {
    content: "";
    height: 0.7em;
    width: 3px;
    background-color: var(--color-1);
    transform: translateY(-50%);
    position: absolute;
    left: 0;
    top: 50%;
  }

  .s-about__list {
    list-style: none;
    font-size: calc(var(--text-size) * 1.05);
    margin-left: 0;

    li {
      font-weight: 500;
      margin-bottom: var(--vspace-0_625);
      padding-left: 0;

      a {
        color: var(--color-text);
      }

      span {
        display: block;
        font-size: var(--text-sm);
        font-weight: 300;
        line-height: 1.2;
        color: var(--color-text-light) !important;
      }
    }
  }
}
</style>