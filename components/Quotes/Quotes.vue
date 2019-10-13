<template>
    <div class="quote">
        <h2>Цитата дня</h2>
        <div>
            <p>„ {{ quotes[quoteCounter].text }} “</p>
            <span>Автор: {{quotes[quoteCounter].name }}</span>
        </div>
        <div class="quote-btn">
            <input type="button" value="Предыдущая цитата"  @click="prevQuote">
            <input type="button" value="Следующая цитата" @click="nextQuote">
            <input type="button" value="Показать все цитаты" @click="showAll" v-if="!allQuotes">
            <input type="button" value="Скрыть все цитаты" @click="hideAll" v-if="allQuotes">
        </div>
        <span>Кличество цитат: {{ quoteCounter + 1 }} / {{ quotes.length }}</span>
        <div v-if="allQuotes">
           <ol>
                <li v-for="(quote, idx) in quotes" :key="idx">
                    <p>{{quote.text}}</p>
                    <span>{{quote.name}}</span>
               </li>
           </ol>
        </div>
    </div>
</template>

<style scoped>

</style>

<script>
    export default {

    }
</script>