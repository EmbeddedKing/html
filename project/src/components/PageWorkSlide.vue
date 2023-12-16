<template>
  <div class="s-testimonials__slide swiper-slide">
    <div class="s-testimonials__author">
      <img :src="imgSrc" alt="Author image" class="s-testimonials__avatar">
      <cite class="s-testimonials__cite">
        <strong>{{ author }}</strong>
        <span>{{ company }}</span>
      </cite>
    </div>
    <p>
      <slot></slot>
    </p>
  </div> <!-- end s-testimonials__slide -->
</template>

<script setup>
defineProps({
  imgSrc: {
    type: String,
    required: true
  },
  author: {
    type: String,
    required: true
  },
  company: {
    type: String,
    required: true
  },
})
</script>

<style lang="scss" scoped>
.s-testimonials__slide {
  position: relative;
  .s-testimonials__author {
    display: inline-block;
    min-height: var(--vspace-2);
    margin-bottom: var(--vspace-0_625);
    padding-left: calc(2.25 * var(--space));
    position: relative;
    .s-testimonials__avatar {
      width: var(--vspace-1_75);
      height: var(--vspace-1_75);
      border-radius: 100%;
      outline: none;
      position: absolute;
      top: 0;
      left: 0;
    }
    .s-testimonials__cite {
      display: block;
      strong,
      span {
        font-style: normal;
        transition: all 0.3s ease-in-out;
      }
      strong {
        font-size: calc(var(--text-size) * 0.9);
        font-weight: 500;
        line-height: var(--vspace-0_75);
        color: var(--color-text-dark);
      }
      span {
        display: block;
        font-size: calc(var(--text-size) * 0.75);
        font-weight: 400;
        line-height: var(--vspace-0_5);
        color: var(--color-text-light);
      }
    }
  }
}

/* ------------------------------------------------------------------- 
 * responsive:
 * works
 * ------------------------------------------------------------------- */
@media screen and (max-width: 800px) {
  .s-testimonials__slide {
    text-align: center;
    .s-testimonials__author {
      .s-testimonials__cite {
        text-align: left;
      }
    }
  }
}
</style>