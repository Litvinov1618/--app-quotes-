<template>
    <div class="quotes">
        <h2>Цитата дня</h2>
        <QuoteWindow :quotes="quotes"></QuoteWindow>
        <AllQuotes :quotes="quotes"></AllQuotes>
    </div>
</template>

<style scoped>
    .quotes {
        border: 2px solid gray;
        border-radius: 15px;
        padding: 10px;
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
        }),
        components: {
            AllQuotes,
            QuoteWindow,
        }     
    }
</script>