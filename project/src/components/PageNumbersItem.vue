<template>
  <div class="column counter-items__item">
    <div class="num">
      {{ number }}
      <span>+</span>
    </div>
    <h5>{{ title }}</h5>
    <p>
      <slot></slot>
    </p>
  </div> <!-- end counter-items__item -->
</template>

<script setup>
defineProps({
  number: {
    type: String,
    request: true
  },
  title: {
    type: String,
    request: true
  },
})
</script>

<style lang="scss" scoped>
/* ===================================================================
 * # NUMBERS
 *
 *
 * ------------------------------------------------------------------- */
.counter-items__item {
  flex: none;
  width: 50%;
  margin-bottom: var(--vspace-0_625);

  .num {
    display: inline-flex;
    align-items: center;
    font-family: var(--font-1);
    font-weight: 700;
    font-size: var(--text-huge-3);
    letter-spacing: -0.035em;
    line-height: 1;
    color: var(--color-3-dark);

    span {
      font-size: 0.5em;
      margin-left: 0.1em;
    }
  }

  h5 {
    font-family: var(--font-1);
    font-weight: 500;
    margin-top: 0;
    margin-bottom: var(--vspace-0_75);
  }
}

/* ------------------------------------------------------------------- 
 * responsive:
 * numbers
 * ------------------------------------------------------------------- */
@media screen and (max-width: 1000px) {
  .counter-items__item {
    .num {
      font-size: var(--text-huge-1);
    }
  }
}

@media screen and (max-width: 700px) {
  .counter-items__item {
    width: 100%;
  }
}
</style>