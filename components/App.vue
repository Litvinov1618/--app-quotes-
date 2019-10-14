<template>
    <div>
        <Header></Header>
        <Quotes></Quotes>
    </div>
</template>


<script>
    import Quotes from './Quotes/Quotes';
    import Header from './Header';
    
    export default {
        components: {
            Quotes,
            Header
        }
    } 
</script>