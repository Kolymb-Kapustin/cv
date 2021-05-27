<template lang="pug">
    v-app(light)
        v-main
            .header

            v-container
                nuxt

            .footer
</template>

<style lang="scss">
@import "~static/scss/main.scss";

.header,
.footer {
    height: 20px;
    width: 100%;
    background: #53809e;
}
</style>
