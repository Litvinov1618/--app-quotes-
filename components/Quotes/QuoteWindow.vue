<template>
    <div>
        <p>„ {{ quotes[quoteCounter].text }} “</p>
        <span>Автор: {{quotes[quoteCounter].name }}</span>
    </div>
</template>

<script>
    export default {
        props: ['quotes', 'quoteCounter']
    }
</script>