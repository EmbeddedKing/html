<template>
  <div id="page" class="s-pagewrap">
    <page-header />
    <page-intro />
    <page-about />
    <page-work />
    <page-numbers />
    <page-footer />
  </div>
</template>

<script setup>
import PageHeader from './PageHeader.vue';
import PageIntro from './PageIntro.vue';
import PageAbout from './PageAbout.vue';
import PageWork from './PageWork.vue';
import PageNumbers from './PageNumbers.vue';
import PageFooter from './PageFooter.vue';
import { onMounted, ref } from 'vue';

onMounted(() => {
  const ssScrollSpy = function () {
    const sections = document.querySelectorAll('.target-section');
    if (!sections)
      return;
    // Add an event listener listening for scroll
    window.addEventListener('scroll', navHighlight);
    function navHighlight() {
      // Get current scroll position
      let scrollY = window.scrollY;
      // Loop through sections to get height(including padding and border), 
      // top and ID values for each
      sections.forEach(function (current) {
        const sectionHeight = current.offsetHeight;
        const sectionTop = current.offsetTop - 50;
        const sectionId = current.getAttribute('id');

        /* If our current scroll position enters the space where current section 
         * on screen is, add .current class to parent element(li) of the thecorresponding 
         * navigation link, else remove it. To know which link is active, we use 
         * sectionId variable we are getting while looping through sections as 
         * an selector
         */
        if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
          console.log('change add' + sectionId);
          document.querySelector('.s-header__nav a[href*=' + sectionId + ']').parentNode.classList.add('current');
        } else {
          console.log('change remove' + sectionId);
          document.querySelector('.s-header__nav a[href*=' + sectionId + ']').parentNode.classList.remove('current');
        }
      });
    }
  };

  const ssAlertBoxes = function () {
    const boxes = document.querySelectorAll('.alert-box');
    boxes.forEach(function (box) {
      box.addEventListener('click', function (e) {
        if (e.target.matches('.alert-box__close')) {
          e.stopPropagation();
          e.target.parentElement.classList.add('hideit');

          setTimeout(function () {
            box.style.display = 'none';
          }, 500)
        }
      });
    })

  }; // end ssAlertBoxes

  const ssMoveTo = function () {

    const easeFunctions = {
      easeInQuad: function (t, b, c, d) {
        t /= d;
        return c * t * t + b;
      },
      easeOutQuad: function (t, b, c, d) {
        t /= d;
        return -c * t * (t - 2) + b;
      },
      easeInOutQuad: function (t, b, c, d) {
        t /= d / 2;
        if (t < 1) return c / 2 * t * t + b;
        t--;
        return -c / 2 * (t * (t - 2) - 1) + b;
      },
      easeInOutCubic: function (t, b, c, d) {
        t /= d / 2;
        if (t < 1) return c / 2 * t * t * t + b;
        t -= 2;
        return c / 2 * (t * t * t + 2) + b;
      }
    }

    const triggers = document.querySelectorAll('.smoothscroll');

    const moveTo = new MoveTo({
      tolerance: 0,
      duration: 1200,
      easing: 'easeInOutCubic',
      container: window
    }, easeFunctions);

    triggers.forEach(function (trigger) {
      moveTo.registerTrigger(trigger);
    });

  }; // end ssMoveTo

  ssScrollSpy()
  ssAlertBoxes()
  ssMoveTo()
})
</script>

<style scoped>
.s-pagewrap {
  display: flex;
  flex-direction: column;
  min-height: 100%;
  overflow: hidden;
  position: relative;
}
</style>