<template>
  <header class="s-header" :class="{
    'open': isOpen,
    'sticky': isSticky
  }">
    <!-- <header class="s-header"> -->
    <div class="row s-header__inner">
      <div class="s-header__block">
        <div class="s-header__logo">
          <a class="logo" href="index.html">
            <img src="/src/images/logo.svg" alt="Homepage">
          </a>
        </div>

        <a class="s-header__menu-toggle" href="#0" @click="clickHandle"><span>Menu</span></a>
      </div> <!-- end s-header__block -->

      <nav class="s-header__nav">
        <ul class="s-header__menu-links">
          <li class="current"><a class="smoothscroll" href="#intro" @click="clickHandle">Intro</a></li>
          <li><a class="smoothscroll" href="#about" @click="clickHandle">About</a></li>
          <li><a class="smoothscroll" href="#works" @click="clickHandle">Works</a></li>
          <li><a class="smoothscroll" href="#footer" @click="clickHandle">Contact</a></li>
        </ul> <!-- s-header__menu-links -->
      </nav> <!-- end s-header__nav -->
    </div> <!-- end s-header__inner -->
  </header> <!-- end s-header -->
</template>

<script setup>
import { onMounted, ref } from 'vue';

const isOpen = ref(false)
const isSticky = ref(false)

const clickHandle = function (event) {
    isOpen.value = !isOpen.value;
}

onMounted(() => {
  const ssMoveHeader = function () {
    const hdr = document.querySelector('.s-header');
    const hero = document.querySelector('#intro');
    let triggerHeight;

    if (!(hdr && hero))
      return;

    const stickyDetect = function () {
      let loc = window.scrollY;
      if (loc >= triggerHeight) {
        isOpen.value = false;
        isSticky.value = true;
      } else {
        isSticky.value = false;
      }
    }

    setTimeout(() => {
      triggerHeight = hero.offsetHeight;
      stickyDetect();
    }, 300);

    window.addEventListener('scroll', stickyDetect);
  };

  const ssMobileMenu = function () {
    const toggleButton = document.querySelector('.s-header__menu-toggle');
    const mainNavWrap = document.querySelector('.s-header__nav');

    if (!(toggleButton && mainNavWrap))
      return;

    window.addEventListener('resize', function () {
      // above 900px
      if (window.matchMedia('(min-width: 901px)').matches) {
        isOpen.value = false
      }
    });
  };

  ssMoveHeader()
  ssMobileMenu()
})
</script>

<style lang="scss" scoped>
.s-header {
  --header-height: 72px;
  --logo-width: 10.2rem;
  --width-grid-max: calc(var(--width-sixteen-cols) - calc(var(--gutter) * 2));
  --box-shadow: 0 1px 1px rgba(0, 0, 0, 0.02),
    0 2px 2px rgba(0, 0, 0, 0.02),
    0 4px 4px rgba(0, 0, 0, 0.02),
    0 8px 8px rgba(0, 0, 0, 0.02);
  --box-shadow-2: 0 2px 2px rgba(0, 0, 0, 0.03),
    0 4px 4px rgba(0, 0, 0, 0.03),
    0 8px 8px rgba(0, 0, 0, 0.03),
    0 16px 16px rgba(0, 0, 0, 0.03);
  z-index: 100;
  background-color: transparent;
  height: var(--header-height);
  width: 100%;
  position: absolute;
  top: min(var(--vspace-0_75), 4vh);
  left: 0;

  .s-header__inner {
    height: var(--header-height);
    align-items: center;
    justify-content: space-between;
    background-color: var(--color-3);
    border: 1px solid rgba(255, 255, 255, 0.03);
    padding: 0 var(--gutter);
    box-shadow: var(--box-shadow);

    transition-property: opacity;
    transition-timing-function: cubic-bezier(0.28, 0.12, 0.22, 1);
    transition-duration: 0.6s;
    transition-delay: 0s;
    opacity: 0;

    .s-header__block {
      z-index: 101;
      position: relative;

      .s-header__logo {
        z-index: 3;
        line-height: 1;
        transform: translate(0.2rem, -0.05em);

        a {
          display: block;
          margin: 0;
          padding: 0;
          outline: 0;
          border: none;

          img {
            width: var(--logo-width);
            margin: 0;
            vertical-align: bottom;
          }
        }
      }

      .s-header__menu-toggle {
        --toggle-block-width: 44px;
        --toggle-line-width: 28px;
        --toggle-line-height: 1px;
        display: none;
        width: var(--toggle-block-width);
        height: var(--toggle-block-width);
        position: absolute;
        top: calc((var(--header-height) - var(--toggle-block-width)) / 2);
        right: calc(var(--gutter) * 2 - 0.8rem);

        span {
          display: block;
          background-color: white;
          width: var(--toggle-line-width);
          height: var(--toggle-line-height);
          margin-top: -1px;
          font: 0/0 a;
          text-shadow: none;
          color: transparent;
          transition: all 0.5s;
          position: absolute;
          right: calc((var(--toggle-block-width) - var(--toggle-line-width)) / 2);
          top: 50%;
          bottom: auto;
          left: auto;
        }

        span::before,
        span::after {
          content: "";
          width: 100%;
          height: 100%;
          background-color: inherit;
          transition: all 0.5s;
          position: absolute;
          left: 0;
        }

        span::before {
          top: -10px;
        }

        span::after {
          bottom: -10px;
        }
      }
    }

    .s-header__nav {
      margin-left: var(--vspace-1);

      .s-header__menu-links {
        list-style: none;
        display: inline-flex;
        flex-flow: row nowrap;
        margin: 0;
        padding: 0;

        li {
          padding-left: 0;

          a {
            display: block;
            font-family: var(--font-1);
            font-weight: 400;
            font-size: 1.5rem;
            line-height: var(--vspace-1);
            color: var(--color-gray-14);
            padding: 0 1.2rem;
            transition-property: color, background-color;
          }
        }

        li.current a {
          color: white;
        }
      }
    }
  }
}

.s-header.sticky {
  box-shadow: var(--box-shadow);
  border: none;
  border-bottom: 1px solid rgba(255, 255, 255, 0.03);
  position: fixed;
  top: 0;
  left: 0;
  animation: anim-s-header-sticky 0.3s linear;
  animation-fill-mode: forwards;

  .s-header__inner {
    --width-grid-max: var(--width-default);
    background-color: transparent;
    border: none;
    box-shadow: none;
  }
}

@keyframes anim-s-header-sticky {
  0% {
    transform: translateY(-100%);
    background-color: transparent;
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    background-color: var(--color-3);
    opacity: 1;
  }
}

.no-js,
.ss-show {
  .s-header {
    .s-header__inner {
      opacity: 1;
      transition-delay: 1.5s;
    }
  }
}

/* ------------------------------------------------------------------- 
 * responsive:
 * site-header
 * ------------------------------------------------------------------- */
@media screen and (max-width: 900px) {
  .s-header {
    --header-height: 80px;
    top: 0;

    .s-header__inner {
      width: 100%;
      margin: 0;
      padding: 0;
      border: none;
      box-shadow: none;

      .s-header__block {
        width: 100%;
        height: var(--header-height);
        box-shadow: var(--box-shadow);
        border: none;
        border-bottom: 1px solid rgba(255, 255, 255, 0.03);

        .s-header__logo {
          position: absolute;
          left: calc(var(--gutter) * 2);
          top: 50%;
          transform: translate(0, -50%);
        }

        .s-header__menu-toggle {
          display: block;
        }
      }

      .s-header__nav {
        display: block;
        width: 100%;
        transform: scaleY(0);
        transform-origin: center top;
        background-color: var(--color-3);
        box-shadow: var(--box-shadow-2);
        border-bottom: 1px solid rgba(255, 255, 255, 0.03);
        padding-top: calc(var(--header-height) + var(--vspace-1_25));
        padding-right: calc(var(--gutter) * 2);
        padding-left: calc(var(--gutter) * 2);
        padding-bottom: var(--vspace-1_5);
        margin: 0;
        position: absolute;
        top: 0;
        left: 0;

        .s-header__menu-links {
          margin: 0;
          transform: translateY(-2rem);
          opacity: 0;
          visibility: hidden;
          display: block;

          li a {
            font-size: var(--text-size);
            padding: var(--vspace-0_25) 0;
          }
        }
      }
    }
  }

  .s-header.sticky {
    box-shadow: none;
    border: none;
  }

  .s-header__contact {
    margin-top: var(--vspace-1_5);

    .btn {
      width: 100%;
      margin: 0;
    }
  }

  .s-header.open {
    height: auto;

    .s-header__inner {
      .s-header__block {
        box-shadow: none;

        .s-header__menu-toggle {
          span {
            background-color: rgba(255, 255, 255, 0);
            transition: all 0.1s;
          }

          span::before,
          span::after {
            background-color: white;
          }

          span::before {
            top: 0;
            transform: rotate(135deg);
          }

          span::after {
            bottom: 0;
            transform: rotate(225deg);
          }
        }
      }

      .s-header__nav {
        transform: scaleY(1);
        transition: transform 0.4s cubic-bezier(0.215, 0.61, 0.355, 1);
        transition-delay: 0s;

        .s-header__menu-links,
        .s-header__contact {
          transform: translateY(0);
          opacity: 1;
          visibility: visible;
          transition: all 0.6s cubic-bezier(0.215, 0.61, 0.355, 1);
          transition-delay: 0.3s;
        }
      }
    }
  }
}

@media screen and (max-width: 600px) {
  .s-header {
    .s-header__inner {
      .s-header__block {
        .s-header__logo {
          left: calc(var(--gutter) * 2 + 2vw);
        }

        .s-header__menu-toggle {
          right: calc(var(--gutter) * 2 + 0.4rem);
        }
      }

      .s-header__nav {
        padding-left: calc(var(--gutter) * 2 + 2.2vw);
        padding-right: calc(var(--gutter) * 2 + 2vw);
      }
    }
  }
}

@media screen and (max-width: 400px) {
  .s-header {
    .s-header__inner {
      .s-header__block {
        .s-header__menu-toggle {
          right: calc(var(--gutter) * 2);
        }
      }
    }
  }
}</style>
