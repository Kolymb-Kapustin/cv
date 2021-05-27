<template lang="pug">
.information
    .information__header {{ item.head }}

    .information__list
        .information__list-item(v-for="(info, key) in item.info")
            span(v-if="isNaN(key)") {{ key[0].toUpperCase() + key.slice(1) }}:&nbsp

            span(
                v-if="info"
                v-html='info'
            )
</template>

<script>
export default {
    props: {
        item: {
            type: [Array, Object],
            required: false,
            default: () => []
        }
    }
}
</script>
<style lang="scss">
@import "~static/scss/vars.scss";

.information {
    margin-bottom: 26px;

    &__header {
        font-size: 20px;
        letter-spacing: 2px;
        font-weight: bold;
        margin-bottom: 8px;
        color: $base-color;
        text-transform: uppercase;
        border-bottom: 1px solid $base-color;
    }

    &__list-item {
        padding: 4px 0;
        border-bottom: 1px dotted #000;

        span {
            font-size: 16px;

            &:nth-child(1) {
                font-weight: bold;
            }
        }
    }
}
</style>
