<template>
    <div class="quotes">
        <h2>Цитата дня</h2>
        <QuoteWindow :quotes="quotes" :quoteCounter="quoteCounter"></QuoteWindow>
        <div class="quotes__btn">
            <input type="button" value="Предыдущая цитата"  @click="prevQuote">
            <input type="button" value="Следующая цитата" @click="nextQuote">
        </div>
        <span>Количество цитат: {{ quoteCounter + 1 }} / {{ quotes.length }}</span>
        <AllQuotes :quotes="quotes"></AllQuotes>
    </div>
</template>

<style scoped>
    .quotes {
        border: 2px solid gray;
        border-radius: 15px;
        padding: 10px;
    }
    .quotes__btn {
        padding: 10px 0;
    }
    .quotes__header {
        margin-top: 5px;
    }
</style>

<script>
    import AllQuotes from './AllQuotes'; 
    import QuoteWindow from './QuoteWindow';
  
    export default {
        data: () => ({
            quotes: [
                {name: 'Лев Толстой', text: 'Величайшие истины - самые простые'},
                {name: 'Джим Керри', text: 'Отчаяние — это толчок к изучению или созданию чего-то нового. Если у вас не бывают периодов отчаяния — вы не развиваетесь.'},
                {name: 'Линус Торвальд', text: 'Интеллект — это способность избегать выполнения работы, но так, чтобы она при этом была сделана.' },
                {name: 'Конфуций', text: 'Счастлив не тот, кто имеет всё лучшее, а тот, кто извлекает всё лучшее из того, что имеет.'},
                {name: 'Эрнест Хемингуэй', text: 'Отличный способ проверить человека - это довериться ему.'},
                {name: 'Оскар Уайльд', text: 'Человек ценен, когда его слова совпадают с его действиями.'},
                {name: 'Леонардо да Винчи', text: 'Ничто так не обманывает нас, как наше мнение.'}
            ],
            quoteCounter: 0,
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
        components: {
            AllQuotes,
            QuoteWindow,
        }     
    }
</script>