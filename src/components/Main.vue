<template>
  <main class="main">
    <div :class="item.classColection" v-for="item in infos" :key="item.id">
        <img :src="item.img" :alt="item.alt" class="main__image">
        <div class="main__about">
            <h1 class="main__title">{{ item.title }}</h1>
            <p class="main__text">{{ item.text }}</p>
            <a :href="item.link" :class="item.classLink">{{ item.textLink }}</a> 
        </div>
    </div>
    <Testimonials />
  </main>
</template>

<script>
    import Testimonials from "./Testimonials.vue";
    
    export default {
    name: "Main",
    components: { 
        Testimonials 
    },
    data() {
        return {
            infos: [
                {
                    classColection: "main__colection",
                    img: "https://user-images.githubusercontent.com/74377158/194156383-3d05d25a-e5ee-47be-b7da-d13ad2144174.jpg",
                    alt: "egg",
                    title: "Transform your brand",
                    text: "We are a full-service creative agency specializing in helping brands grow fast. Engage your clients through compelling visuals that do most of the marketing for you.",
                    link: "#",
                    textLink: "Learn More",
                    classLink: "main__link yellow"
                },
                {
                    classColection: "main__colection left",
                    img: "https://user-images.githubusercontent.com/74377158/194156376-a263f6ab-5c47-4562-84e0-bdc2563412fe.jpg",
                    alt: "cup",
                    title: "Stand out to the right audience",
                    text: "Using a collaborative formula of designers, researches, photographers, videographers and copywriters, we will build and extend your brand in digital places.",
                    link: "#",
                    textLink: "Learn More",
                    classLink: "main__link red"
                },
                {
                    classColection: "main__colection",
                    img: "https://user-images.githubusercontent.com/74377158/194156365-874b1ec8-2de1-483a-ace4-82e526042734.jpg",
                    alt: "cherry",
                    title: "Graphic Design",
                    text: "Great design makes your memorable. We deliver artwork that underscores your brand message and captures potential clients attention.",
                    link: "#",
                    textLink: "Learn More",
                    classLink: "main__link green"
                },
                {
                    classColection: "main__colection left",
                    img: "https://user-images.githubusercontent.com/74377158/194156374-8ff03d23-cbf6-4aa9-a635-f57f9cb49bda.jpg",
                    alt: "orange",
                    title: "Photography",
                    text: "Increase your credibility by getting the most stunning, high-quality photos that improve your business image.",
                    link: "#",
                    textLink: "Learn More",
                    classLink: "main__link blue"
                }
            ]
        }
    }
}

</script>

<style lang="scss">
    @import '../assets/_variables.scss';

    .main {

        &__colection {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
            flex-direction: row-reverse;
            width: 100%;

            &.left {
                flex-direction: inherit;
            }

            @include phone {
                flex-direction: column;
            }

            
            @include tablet {
                flex-direction: column;
            }
        }

        &__image {
            width: 50%;

            @include phone {
                width: 100%;
            }

            @include tablet {
                width: 100%;
            }
        }

        &__about {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 50%;
            text-align: center;
            flex-direction: column;

            @include phone {
                width: 100%;
                margin-top: 1rem;
                margin-bottom: 1rem;
            }

            @include tablet {
                width: 80%;
                margin-top: 2rem;
                margin-bottom: 2rem;
            }
        }

        &__title, &__text {
            margin-bottom: 1rem;
        }

        &__text {
            width: 50%;

            @include phone {
                width: 80%;
            }

            @include tablet {
                width: 80%;
            }
        }

        &__title {
            color: $veryDarkBlue;
            font-size: 40px;
            font-family: $fraunces;
        }

        &__text {
            color: $darkGrayish;
            font-weight: bold;
            line-height: 2;
        }

        &__link {
            text-decoration: none;
            color: $veryDarkBlue;
            font-family: $fraunces;
            font-size: 16px;
            text-transform: uppercase;

            &.yellow, &.red, &.green, &.blue {
                &:hover {
                    border-bottom: 4px solid $yellow;
                    width: 7.5rem;
                }
            }

            &.red {
                &:hover {
                    border-bottom: 4px solid $softRed;
                }
            }

            &.green {
                &:hover {
                    border-bottom: 4px solid $darkModerateCyan;
                }
            }

            &.blue {
                &:hover {
                    border-bottom: 4px solid $darkBlue;
                }
            }
        }
    }

</style>