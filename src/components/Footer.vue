<template>
    <footer class="footer">
        <h1 class="footer__title">sunnyside</h1>
        <div class="footer__info">
            <ul class="footer__list">
                <li v-for="item in list" :key="item.id">
                    <a :href="item.link">{{ item.name }}</a>
                </li>
            </ul>
        </div>
        <div class="footer__media">
            <ul class="footer__social">
                <li v-for="media in social" :key="media.id">
                    <a :href="media.link">
                        <img class="footer__image" :src="media.image" :alt="media.name">
                    </a>
                </li>
            </ul>
        </div>
    </footer>
</template>

<script>
    export default {
        name: 'Footer',
        data() {
            return {
                list: [
                    { link: '#', name: 'About' }, { link: '#', name: 'Services' }, { link: '#', name: 'Projects' }
                ],
                social: [
                    { link: '#', name: 'facebook', image: 'https://user-images.githubusercontent.com/74377158/194156339-b50e095e-de21-4c47-a903-72ee3e910b6f.svg' },
                    { link: '#', name: 'instagram', image: 'https://user-images.githubusercontent.com/74377158/194156346-e34db341-d31f-4698-bb1b-e4e403cd53ca.svg' },
                    { link: '#', name: 'twitter', image: 'https://user-images.githubusercontent.com/74377158/194156351-b8ff0199-d2ee-4975-81d8-ca91eddecd25.svg' },
                    { link: '#', name: 'pinterest', image: 'https://user-images.githubusercontent.com/74377158/194156350-30da39d0-bc06-4509-8952-509944fd5e9e.svg' },
                ]
            }
        }
    }
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .footer {
        background-color: $cyan;
        color: $darkCyan;
        height: 15rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;

        &__title {
            font-size: 30px;
            font-weight: bold;
        }

        a {
            text-decoration: none;

            &:hover {
                color: $white;
            }
        }

        ul {
            display: flex;
            align-items: center;
            padding: 1rem;
        }

        li {
            padding: 1rem;
        }
    }

</style>