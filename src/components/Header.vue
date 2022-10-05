<template>
  <header class="header">
    <div class="header__content">
      <div class="header__title">
        <h1>{{ title }}</h1>
      </div>
      <div class="header__info">
        <img class="header__bars" src="../../public/images/icon-hamburger.svg" alt="">
        <ul class="header__list">
          <li v-for="content in items" :key="content.id">
            <a :href="content.link">{{ content.name }}</a>
          </li>
          <button class="header__button">Contact</button>
        </ul>
      </div>
    </div>
    <div class="header__text">
      <h1>{{ text }}</h1>
      <img :src="image" :alt="altImage" class="header__img">
    </div>
  </header>
</template>

<script>
  
  export default {
    name: 'Header',
    data() {
      return {
        title: 'sunnyside',
        text: 'We are creative',
        image: '../../public/images/icon-arrow-down.svg',
        altImage: 'arrow down',
        items: [
          {link: '#', name: 'About'}, {link: '#', name: 'Services'}, {link: '#', name: 'Projects'}
        ],

        nav() {
          $(".header__bars").click(() => {
            $(this).toggleClass("active")
            $(".header__list").toggleClass("active")
            $(".header__button").toggleClass("active")
          })
        }
      }
    },
    mounted() {
      this.nav()
    }
  }
  
</script>

<style lang="scss">
  @import '../assets/_variables.scss';

  .header {
    background-image: url('../../public/images/image-header.jpg');
    background-size: cover;
    height: calc(100vh - 30px);
    padding: 1rem;
    color: $white;
    font-size: 20px;
    
    &__content {
      display: flex;
      justify-content: space-around;
      align-items: center;

      @include phone {
        justify-content: inherit;
        flex-wrap: wrap;
        height: 1rem;
      }

      @include tablet {
        justify-content: inherit;
        flex-wrap: wrap;
        height: 1rem;
      }
    }

    &__title {
      font-weight: bold;
      font-family: $fraunces;
    }

    &__info {

      @include phone {
        width: 100%;
        padding: 1rem;
      }

      @include tablet {
        width: 100%;
        padding: 1rem;
      }
    }

    &__bars {
      display: none;
      
      @include phone {
        display: block;
        float: right;
        margin-top: -2rem;
      }

      @include tablet {
        display: block;
        float: right;
        margin-top: -2rem;
      }
    }

    &__list {
      display: flex;
      align-items: center;

      li {
        padding: .5rem;

        a {
          text-decoration: none;
          color: inherit;
        }
      }
      
      @include phone {
        color: $darkBlue;
        flex-direction: column;
        justify-content: space-evenly;
        text-align: center;    
        opacity: 0;
        visibility: hidden;
        margin: 0rem -1.5rem 0 -1.5rem;
        transform: translate3d(0, -50px, 0);
        transition: .3s;
        background: $white;
        height: 20rem;

        &.active {
          visibility: visible;
          opacity: 1;
          transform: translate3d(0, 0, 0)
        }
      }

      @include tablet {
        color: $darkBlue;
        flex-direction: column;
        justify-content: space-evenly;
        text-align: center;    
        opacity: 0;
        visibility: hidden;
        margin: 0rem -1.5rem 0 -1.5rem;
        transform: translate3d(0, -50px, 0);
        transition: .3s;
        background: $white;
        height: 20rem;

        &.active {
          visibility: visible;
          opacity: 1;
          transform: translate3d(0, 0, 0)
        }
      }
    }

    &__button {
      background-color: $white;
      border: none;
      border-radius: 20px;
      padding: .9rem;
      font-weight: bold;
      text-transform: uppercase;
      cursor: pointer;
      transition: 1s;

      &:hover {
        background-color: $grayish;
        color: $white;
      }

      @include phone {
        background-color: $yellow;
      }

      @include tablet {
        background-color: $yellow;
      }
    }

    &__text {
      font-family: $fraunces;
      font-size: 50px;
      font-weight: 100;
      text-transform: uppercase;
      text-align: center;
      margin-top: 5rem;

      h1 {
        line-height: 2;
      }
    }

    &__img {
      width: 5rem;
    }
  }

</style>