<template lang="pug">
.history
    .history__header Timeline

    v-timeline.history__timeline(dense)
        v-timeline-item(
            v-for="(year, i) in years",
            color="#53809e"
            :key="i",
        )
            template(v-slot:opposite)
                span.v-timeline-item__year(v-text="year.year")

            .v-timeline-item__main-content
                h3.v-timeline-item__title {{year.title}}

                .v-timeline-item__description(v-html='year.description')
</template>

<script>
export default {
    data () {
        return {
            years: [
                {
                    title: 'Blackbit Digital (2023 — 2025) International Digital Agency',
                    description: 'IT company </br> <a href="https://jobs.dou.ua/companies/yellow-stone"/>https://jobs.dou.ua/companies/yellow-stone</a> </br> <a href="https://jobs.dou.ua/companies/evoplay/"/>https://jobs.dou.ua/companies/evoplay/</a></br> I work here with lots of projects and use Vue/Nuxt/Less/PUG/BEM',
                    year: '2019'
                },
                {
                    title: 'Yellow Stone (Evoplay)',
                    description: 'IT company </br> <a href="https://jobs.dou.ua/companies/yellow-stone"/>https://jobs.dou.ua/companies/yellow-stone</a> </br> <a href="https://jobs.dou.ua/companies/evoplay/"/>https://jobs.dou.ua/companies/evoplay/</a></br> I work here with lots of projects and use Vue/Nuxt/Less/PUG/BEM',
                    year: '2019'
                },
                {
                    title: 'Epicentr',
                    description: 'The largest construction online store in Ukraine <a href="https://epicentrk.ua/">https://epicentrk.ua/</a>',
                    year: '2018'
                },
                {
                    title: 'Yamasters',
                    description: 'Web Studio <a href="https://yamasters.com.ua/">https://yamasters.com.ua/</a>',
                    year: '2017'
                },
                {
                    title: 'Freelance',
                    description: 'The first steps on my way',
                    year: '2016'
                }
            ]
        }
    }
}
</script>
<style lang="scss">
@import "~static/scss/vars.scss";

.history {
    &__header {
        font-size: 20px;
        letter-spacing: 2px;
        font-weight: bold;
        margin-bottom: 20px;
        color: $base-color;
        text-transform: uppercase;
        border-bottom: 1px solid $base-color;
    }

    &__timeline {
        margin-left: 40px;
        max-width: 100%;

        &.v-timeline--dense .v-timeline-item__opposite {
            left: -38px;
            display: block;
            position: absolute;
        }
    }

    .v-timeline {
        &:before {
            width: 10px;
            margin-left: -4px;
        }

        .v-timeline-item {
            &__body {
                .headline {
                    font-size: 20px!important;
                    font-weight: bold!important;
                    margin-bottom: 2px!important;
                }
            }

            &__opposite {
                width: 54px;
                height: 28px;
                display: flex;
                color: #fff;
                align-items: center;
                justify-content: center;
                background: $base-color;

                &:after {
                    width: 0;
                    height: 0;
                    content: '';
                    right: -11px;
                    position: absolute;
                    border-style: solid;
                    display: inline-block;
                    border-width: 14px 0 14px 11.2px;
                    border-color: transparent transparent transparent $base-color;
                }
            }

            &__year {
                font-size: 17px;
                font-weight: bold;
                padding-left: 2px;
            }

            &__dot {
                display: flex;
                box-shadow: none;
                align-items: center;
                justify-content: center;
                background: $background-color;

                .v-timeline-item__inner-dot {
                    width: 22px;
                    height: 22px;
                }
            }

            &__description {
                a {
                    word-break: break-all;
                }
            }
        }
    }
}
</style>
