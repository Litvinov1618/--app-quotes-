<template>
    <div>
        <div class="buttons-outer">
            <input type="button" value="Показать все цитаты" @click="showAll" v-if="!allQuotes">
            <input type="button" value="Скрыть все цитаты" @click="hideAll" v-else>
        </div>
        <ol v-if="allQuotes">
            <li class="item" v-for="quote of quotes" :key="quote.text">
                <p>"{{quote.text}}"</p>
                <small>{{quote.name}}</small>
            </li>
        </ol>
    </div>
</template>

<style lang="scss" scoped>
    .item {
        font-size: 18px;
        padding-bottom: 10px;

        small {
            color: grey;
        }
    }
    .buttons-outer {
        padding: 10px 0;
    }
</style>


<script>
    export default {
        data: () => ({
            allQuotes: false,
        }),
        props: ['quotes'],
        methods: {
            showAll () {this.allQuotes = true},
            hideAll () {this.allQuotes = false}
        }
    }
</script>

