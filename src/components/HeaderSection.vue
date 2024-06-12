<script setup>
import { headNavs } from '@/constants';
</script>
<template>
  <header id="header" role="banner">
    <div class="header__inner">
      <h1 class="header__logo">
        <a href="">portfolio <em>vue.js</em></a>
      </h1>
      <div class="header__nav" :class="{ show: isNavVisible }" role="navigation" aria-label="메인 메뉴">
        <ul>
          <li v-for="(nav, key) in headNavs" :key="key">
            <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
          </li>
        </ul>
      </div>
      <div id="headerToggle" class="header__nav__mobile" aria-controls="primary-menu" aria-expanded="false" role="button" tabindex="0" @click="toggleMobileMenu">
        <span></span>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      isNavVisible: false
    };
  },
  methods: {
    toggleMobileMenu() {
      this.isNavVisible = !this.isNavVisible;
    },
    scrollLink(event) {
      event.preventDefault();
      const targetId = event.target.getAttribute('href');
      const targetElement = document.querySelector(targetId);
      if (targetElement) {
        targetElement.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
};
</script>

<style lang="scss">
@import '@/assets/scss/_mixin.scss';

#header {
  @include position-fixed;
  z-index: 100000;
  .header__inner {
    @include flex-between;
    background-color: rgba(116, 99, 99, 0.1);
    backdrop-filter: blur(15px);
    padding: 1rem;
    .header__logo {
      font-size: 1.9rem;
      text-align: center;
      text-transform: uppercase;
      line-height: 1;
      em {
        font-size: 13px;
        display: block;
        color: var(--black200);
        font-weight: 400;
      }
    }
    .header__nav {
      @media (max-width: 800px) {
        display: none;
        &.show {
          display: block;
          ul {
            display: block;
            position: absolute;
            top: 68px;
            right: 0px;
            background-color: rgba(166, 99, 99, 0.1);
            backdrop-filter: blur(15px);
            z-index: 1000;
            min-width: 150px;
            padding: 20px 0px;
            li {
              display: block;
              text-align: center;
              a {
                display: inline-block;
                padding: 10px;
              }
            }
          }
        }
        &.show + .header__nav__mobile span::before {
          width: 20px;
        }
        &.show + .header__nav__mobile span::after {
          width: 20px;
        }
      }
      li {
        display: inline;
        a {
          text-transform: uppercase;
          font-size: 1rem;
          padding: 14px;
          position: relative;
          font-weight: 400;
          &::before {
            content: '';
            height: 1px;
            width: 0%;
            background-color: var(--black);
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            transition: all 0.3s ease;
          }
          &:hover::before {
            width: calc(100% - 28px);
          }
        }
      }
    }
    .header__nav__mobile {
      width: 40px;
      height: 40px;
      display: none;
      cursor: pointer;
      @media (max-width: 800px) {
        display: block;
      }
      span {
        display: block;
        width: 40px;
        height: 2px;
        margin-top: 19px;
        background-color: var(--black);
        position: relative;
        &::before {
          content: '';
          width: 40px;
          height: 2px;
          background-color: var(--black);
          position: absolute;
          right: 0px;
          top: 6px;
          transition: width 0.3s ease;
        }
        &::after {
          content: '';
          width: 40px;
          height: 2px;
          background-color: var(--black);
          position: absolute;
          right: 0px;
          bottom: 6px;
          transition: width 0.3s ease;
        }
      }
    }
  }
}
</style>
