<template lang="pug">
v-row
    v-col(cols='12' md='6' lg='8')
        .cover-block
            .cover-block__foto
                img(
                    src='~static/img/avatar.jpg'
                    @click='imgClick'
                )

            .cover-block__text
                span Nick Kapustin
                span Developer

        v-row
            v-col(cols='12' sm='12' lg='5')
                template(v-for='item in infoList')
                    List(:item='item')

            v-col(cols='12' sm='12' lg='7')
                Timeline

    v-col(class='py-0 align-md-stretch' cols='12' md='6' lg='4')
        AboutMe
</template>

<script>
import List from '~/components/List.vue'
import AboutMe from '~/components/AboutMe.vue'
import Timeline from '~/components/Timeline.vue'

export default {
    components: {
        List,
        AboutMe,
        Timeline
    },

    data () {
        return {
            infoList: [
                {
                    head: 'personal',
                    info: {
                        name: 'Nikolay Kapustin',
                        birthday: '4th March 1996 (25)',
                        languages: 'English(B2) Ukrainian Russian',
                        nationality: 'Ukraine'
                    }
                },
                {
                    head: 'skills',
                    info: [
                        'Node, Nuxt',
                        'Vue Vuex Vuetify',
                        'JavaScript Jquery',
                        'CSS (LESS) (SASS) (SCSS)',
                        'Sequlilize (SQL) Mongoose (Mongodb)'
                    ]
                },
                {
                    head: 'work',
                    info: {
                        experience: '4,5 years',
                        currently: 'JS Developer',
                        stack:
                            'Sequalize, Sql, Node, Nuxt, Vue, Vuex, JavaScript'
                    }
                },
                {
                    head: 'education',
                    info: {
                        courses: 'Lectrum Node Backend Courses (lectrum.io)',
                        'it-school': '"Main Academy" Web Developer (mainacademy.ua)',
                        'high-school': 'Lugansk, School gymnasium №60',
                        'english-school': 'English Prime',
                        'specialized-school':
                            'Lviv, Higher vocational school №20 - Computer`s operator'
                    }
                }
            ]
        }
    },

    methods: {
        imgClick (event) {
            window.open(event.target.src)
        }
    }
}
</script>

<style lang='scss'>
@import "~static/scss/vars.scss";

.cover-block {
    display: flex;
    color: $base-color;
    align-items: center;
    justify-content: left;
    min-height: 400px;
    flex-wrap: wrap;

    &__foto {
        width: 286px;
        height: 286px;
        min-width: 286px;
        display: flex;
        overflow: hidden;
        position: relative;
        border-radius: 50%;
        margin-right: 40px;
        transition: all 0.5s;

        img {
            width: 300px;
            position: absolute;
            left: -10px;
        }

        &:hover {
            width: 300px;
            height: 360px;
            cursor: pointer;
            border-radius: 0%;
        }
    }

    &__text {
        display: flex;
        margin: 20px 0px;
        flex-direction: column;

        span {
            letter-spacing: 2px;
            text-transform: uppercase;

            &:nth-child(1) {
                line-height: 1;
                font-size: 38px;
                font-weight: bold;
                margin-bottom: 4px;
            }
            &:nth-child(2) {
                color: #a6bcce;
                font-size: 30px;
            }
        }
    }

    @media screen and (max-width: 960px) {
        justify-content: center;

        &__foto {
            width: 240px;
            height: 240px;
            min-width: 240px;

            img {
                width: 260px;
            }
        }
    }
}
</style>
