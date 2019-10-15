<template>
    <li class="item">
        <p>"{{quote.text}}"</p>
        <small>{{quote.name}}</small>
    </li>
</template>

<style lang="scss" scoped>
    .item {
        font-size: 18px;
        padding-bottom: 10px;

        small {
            color: grey;
        }
    }
</style>


<script>
    export default {
        props: ['quote']
    }
</script>

