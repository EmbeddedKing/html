<template>
    <div class="column entry">
      <a :href="imgHref" class="entry__link glightbox"
        :data-glightbox="'title: ' + (entryTitle) + '; description: .entry__desc-' + (entryNumber)">
        <div class="entry__thumb">
          <!-- <slot name="img"></slot> -->
          <img :src="imgSrc"
            :srcset="imgSrcset" alt="">
        </div>
        <div class="entry__info">
          <h4 class="entry__title">{{ entryTitle }}</h4>
          <div class="entry__cat">{{ entryCat }}</div>
        </div>
      </a>

      <div :class="'glightbox-desc entry__desc-' + (entryNumber)">
        <p>
          <slot></slot>
        </p>
      </div>
    </div> <!-- entry -->
</template>

<script setup>
import { onMounted } from "vue";

defineProps({
  entryNumber: {
    type: Number,
    required: true
  },
  entryTitle: {
    type: String,
    required: true
  },
  entryCat: {
    type: String,
    required: true
  },
  imgHref: {
    type: String,
    required: true
  },
  imgSrc: {
    type: String,
    required: true
  },
  imgSrcset: {
    type: String,
    required: true
  },
})

onMounted(() => {
  const ssGLightbox = function () {
    const lightbox = GLightbox({
      selector: '.glightbox',
      zoomable: false,
      touchNavigation: true,
      loop: false,
      autoplayVideos: true,
      svg: {
        close: '<svg clip-rule="evenodd" fill-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="2" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="m12 10.93 5.719-5.72c.146-.146.339-.219.531-.219.404 0 .75.324.75.749 0 .193-.073.385-.219.532l-5.72 5.719 5.719 5.719c.147.147.22.339.22.531 0 .427-.349.75-.75.75-.192 0-.385-.073-.531-.219l-5.719-5.719-5.719 5.719c-.146.146-.339.219-.531.219-.401 0-.75-.323-.75-.75 0-.192.073-.384.22-.531l5.719-5.719-5.72-5.719c-.146-.147-.219-.339-.219-.532 0-.425.346-.749.75-.749.192 0 .385.073.531.219z"/></svg>',
        prev: '<svg clip-rule="evenodd" fill-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="2" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="m9.474 5.209s-4.501 4.505-6.254 6.259c-.147.146-.22.338-.22.53s.073.384.22.53c1.752 1.754 6.252 6.257 6.252 6.257.145.145.336.217.527.217.191-.001.383-.074.53-.221.293-.293.294-.766.004-1.057l-4.976-4.976h14.692c.414 0 .75-.336.75-.75s-.336-.75-.75-.75h-14.692l4.978-4.979c.289-.289.287-.761-.006-1.054-.147-.147-.339-.221-.53-.221-.191-.001-.38.071-.525.215z" fill-rule="nonzero"/></svg>',
        next: '<svg clip-rule="evenodd" fill-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="2" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="m14.523 18.787s4.501-4.505 6.255-6.26c.146-.146.219-.338.219-.53s-.073-.383-.219-.53c-1.753-1.754-6.255-6.258-6.255-6.258-.144-.145-.334-.217-.524-.217-.193 0-.385.074-.532.221-.293.292-.295.766-.004 1.056l4.978 4.978h-14.692c-.414 0-.75.336-.75.75s.336.75.75.75h14.692l-4.979 4.979c-.289.289-.286.762.006 1.054.148.148.341.222.533.222.19 0 .378-.072.522-.215z" fill-rule="nonzero"/></svg>'
      }
    });
  } // end ssGLightbox
  ssGLightbox()
})
</script>

<style lang="scss" scoped>
.entry {
  flex: none;
  width: 50%;
  margin: 0;
  padding: 0;
  overflow: hidden;
  position: relative;
  .entry__link {
    display: block;
    position: relative;
    img {
      vertical-align: bottom;
      transition: all 0.3s ease-in-out;
      margin: 0;
    }
    .entry__info {
      z-index: 2;
      transform: translate(-50%, 100%);
      opacity: 0;
      visibility: hidden;
      text-align: center;
      position: absolute;
      top: 50%;
      left: 50%;

      .entry__cat,
      .entry__title {
        font-family: var(--font-1);
      }

      .entry__cat {
        font-size: calc(var(--text-size) * 0.8);
        line-height: 1.75;
        color: var(--color-gray-15);
      }

      .entry__title {
        font-weight: 500;
        font-size: var(--text-size);
        line-height: 1.2;
        margin-top: 0;
        margin-bottom: var(--vspace-0_125);
        color: white;
      }
    }
  }

  .entry__link::before {
    z-index: 1;
    content: "";
    display: block;
    background-color: var(--color-text-dark);
    width: 100%;
    height: 100%;
    transition: all, 0.3s cubic-bezier(0.215, 0.61, 0.355, 1);
    opacity: 0;
    visibility: hidden;
    position: absolute;
    top: 0;
    left: 0;
  }
}

.entry:focus,
.entry:hover {
  .entry__link {
    .entry__info {
      transform: translate(-50%, -50%);
      transition: all 0.3s cubic-bezier(0.215, 0.61, 0.355, 1);
      transition-delay: 0.3s;
      opacity: 1;
      visibility: visible;
    }
  }
  .entry__link::before {
    opacity: 1;
    visibility: visible;
  }
}

/* ------------------------------------------------------------------- 
 * responsive:
 * works
 * ------------------------------------------------------------------- */
@media screen and (max-width: 800px) {
  .entry {
    .entry__link {
      .entry__info {
        .entry__title {
          font-size: calc(var(--text-size) * 0.85);
        }
        .entry__cat {
          font-size: calc(var(--text-size) * 0.7);
        }
      }
    }
  }
      
}

@media screen and (max-width: 500px) {
  .entry {
    width: 100%;
  }
}
</style>