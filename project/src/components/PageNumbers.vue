<template>
  <!-- # numbers
        ================================================== -->
  <section id="numbers" class="s-numbers">
    <div class="row counter-items">
      <page-numbers-item number="80" title="Happy Customers">
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Vel harum magni quae voluptate error quo repellendus inventore
        laborum ex veniam.
      </page-numbers-item>
      <page-numbers-item number="120" title="Projects Completed">
        Nunc interdum lacus sit amet orci. Vestibulum dapibus nunc ac augue.
        Fusce vel dui. In ac felis
        quis tortor malesuada pretium
      </page-numbers-item>
      <page-numbers-item number="23k" title="Lines of Code">
        Excepturi nam cupiditate culpa doloremque deleniti repellat. Veniam quos repellat voluptas animi adipisci.
        Nisi eaque consequatur. Voluptatem dignissimos ut ducimus
      </page-numbers-item>
      <page-numbers-item number="85" title="Positive Feedback">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel harum magni quae voluptate error
        quo repellendus inventore laborum ex veniam.
      </page-numbers-item>
    </div> <!-- end counter-items -->
  </section> <!-- end s-numbers -->
</template>

<script setup>
import PageNumbersItem from './PageNumbersItem.vue';
</script>

<style lang="scss" scoped>
.s-numbers {
  padding-top: var(--vspace-5_5);
  padding-bottom: var(--vspace-4);
  background-color: var(--color-gray-10);
  color: var(--color-text-light);
}
</style>