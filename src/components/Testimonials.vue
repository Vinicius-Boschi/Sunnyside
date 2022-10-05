<template>
    <div class="main__testimonials">
        <h1 class="main__title-people">{{ title }}</h1>
        <section class="main__people">
            <div class="main__content" v-for="item in content" :key="item.id">
                <img class="main__img" :src="item.img" :alt="item.name">
                <p class="main__text-people">{{ item.text }}</p>
                <h3 class="main__name">{{ item.name }}</h3>
                <span class="main__job">{{ item.job }}</span>
            </div>
        </section>
        <div class="main__images">
            <img :src="milkbottle" :alt="name">
            <img :src="orange" :alt="nameTwo">
            <img :src="cone" :alt="nameThree">
            <img :src="sugarcubes" :alt="nameFour">
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Testimonials',
        data() {
            return {
                title: 'Client testimonials',
                milkbottle: 'https://user-images.githubusercontent.com/74377158/194156359-aa05d0b8-d428-4cdd-a86a-6b4fcbe1c339.jpg', name: 'milkbottle',
                orange: 'https://user-images.githubusercontent.com/74377158/194156360-deb763aa-ce70-4722-8b28-04ac8712e030.jpg', nameTwo: 'orange',
                cone: 'https://user-images.githubusercontent.com/74377158/194156355-754fe33f-f088-4ba7-a486-9a19e98d278e.jpg', nameThree: 'cone',
                sugarcubes: 'https://user-images.githubusercontent.com/74377158/194156362-762dfc93-41e3-4699-a606-0b3059474f04.jpg', nameFour: 'sugarcubes',

                content: [
                    {
                        img: "https://user-images.githubusercontent.com/74377158/194156353-8ea7aaea-b233-43ea-b8ed-8f7ee1870805.jpg", text: "We put our trust in Sunnyside and they delivered, making sure our needs were met and deadlines were always hit.", name: "Emily R.", job: "Marketing Director"
                    },
                    {
                        img: "https://user-images.githubusercontent.com/74377158/194156380-db4ae76f-9d10-48a0-b377-1eb7bd95cb56.jpg", text: "Sunnyside's enthusiasm coupled with their keen interest in our brand's success made it a satisfying and enjoyable experience.", name: "Thomas S.", job: "Chief Operating Officer"
                    },
                    {
                        img: "https://user-images.githubusercontent.com/74377158/194156371-236e7947-0362-41df-a2de-b1bc66178718.jpg", text: "Incredible end result! Our sales incresead over 400% when we worked with Sunnyside. Highly recommended.", name: "Jennie F.", job: "Business Owner"
                    }
                ]
            }
        }
    }
</script>

<style lang="scss">
    @import '../assets/_variables.scss';

    .main {

        &__testimonials {
            margin-top: 3rem;
        }

        &__title-people {
            text-align: center;
            text-transform: uppercase;
            letter-spacing: .3rem;
            padding: 2rem;
            color: $darkGrayish;
            font-size: 22px;
            font-weight: bold;
            font-family: $fraunces;
        }

        &__people {
            display: grid;
            grid-template-columns: repeat(3, 1fr);

            @include phone {
                grid-template-columns: repeat(1, 1fr);
            }

            @include tablet {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        &__content {
            display: flex;
            flex-direction: column;
            align-items: center;

            @include phone {
                margin-bottom: 2rem;
            }

            @include tablet {
                margin-bottom: 2rem;
            }
        }

        &__img, &__text-people, &__name {
            margin-bottom: 2rem;
        }

        &__img {
            border-radius: 50%;
            width: 15%;
        }

        &__text-people {
            width: 60%;
            color: $veryDarkBlue;
            font-weight: bold;
            line-height: 1.5;
            text-align: center;
        }

        &__name {
            color: $black;
            font-family: $fraunces;
            font-weight: bold;
            font-size: 20px;
        }

        &__job {
            color: $darkGrayish;
        }

        &__images {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            margin-top: 5rem;

            img {
                width: 100%;
            }

            @include phone {
                grid-template-columns: repeat(1, 1fr);
            }

            @include tablet {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    }

</style>