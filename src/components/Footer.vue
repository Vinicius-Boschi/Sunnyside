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
                    { link: '#', name: 'facebook', image: '../../public/images/icon-facebook.svg' },
                    { link: '#', name: 'instagram', image: '../../public/images/icon-instagram.svg' },
                    { link: '#', name: 'twitter', image: '../../public/images/icon-twitter.svg' },
                    { link: '#', name: 'pinterest', image: '../../public/images/icon-pinterest.svg' },
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