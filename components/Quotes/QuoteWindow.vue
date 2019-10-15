<template>
    <div>
        <p>„ {{ quotes[quoteCounter].text }} “</p>
        <span>Автор: {{quotes[quoteCounter].name }}</span>
        <div>
            <div class="quotes__btn">
                <input type="button" value="Предыдущая цитата"  @click="prevQuote">
                <input type="button" value="Следующая цитата" @click="nextQuote">
            </div>
            <span>Количество цитат: {{ quoteCounter + 1 }} / {{ quotes.length }}</span>
        </div>
    </div>
</template>

<script>
    export default {
        data: () => ({
            quoteCounter: 0
        }),
        methods: {
            stepQuote (step) {
                this.quoteCounter += step;
                if (this.quoteCounter >= this.quotes.length)
                    this.quoteCounter = 0;
                if (this.quoteCounter < 0)
                    this.quoteCounter = this.quotes.length - 1;
            },
            nextQuote () {this.stepQuote(1)},
            prevQuote () {this.stepQuote(-1)},
        },
        props: ['quotes']
    }
</script>

<style>
    .quotes__btn {
        padding: 10px 0;
    }
    .quotes__header {
        margin-top: 5px;
    }
</style>