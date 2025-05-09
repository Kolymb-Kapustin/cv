<template lang="pug">
.about-me
    .about-me__head.d-none.d-md-flex
        span CALL ME
        span +38 095 747 14 31

    .about-me__title About me

    .about-me__text
        div Hi, my name is Nikolay, I'm 27 and I'm a developer, I love my job because I like creating, developing products, seeing satisfied customers, and growing like a professional. This is a resume to get the very job where it will be pleasant for us to cooperate and achieve more.
        br
        div Well, a little about my experience - I have been working with Vue almost from the very beginning of my career, how much jquery code has been rewritten)) and how much has been written from scratch more.

    .about-me__contacts
        List(:item='contacts')
</template>

<script>
import List from '~/components/List.vue'

export default {
    components: {
        List
    },

    data () {
        return {
            contacts: {
                head: 'contacts',
                info: {
                    mobile: '<a href="tel:+380957471431">+38(095)747-14-31</a>',
                    email: '<a href="mailto:kolymb.kapustin@icloud.com">kolymb.kapustin@icloud.com</a>',
                    skype: '<a href="skype:live:9eb67247d69b5454?chat">live:9eb67247d69b5454</a>'
                }
            }
        }
    }
}
</script>
<style lang="scss">
@import "~static/scss/vars.scss";

.about-me {
    top: 0;
    height: 100%;
    position: relative;
    background: #edf1f5;
    padding: 40px;

    &__head {
        color: #a6bcce;
        display: flex;
        flex-direction: column;
        padding-top: 129px;
        margin-bottom: 156px;

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
                font-size: 30px;
            }
        }
    }

    &__title {
        font-size: 20px;
        letter-spacing: 2px;
        font-weight: bold;
        margin: 20px 0;
        color: #53809e;
        text-transform: uppercase;
        border-bottom: 1px solid #53809e;
    }

    &__text {
        letter-spacing: 1px;
        margin-bottom: 26px;
    }
}
</style>
