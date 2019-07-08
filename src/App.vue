<template>
    <div class="container">
        <Header :maxQuotes="maxQuotes" :quoteCount="quotes.length"/>
        <NewQuote @quoteAdded="newQuote"></NewQuote>
        <QuoteGrid :quotesArray="quotes" @quoteDeleted="deleteQuote"></QuoteGrid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
        data: function () {
         return {
           maxQuotes: 10,
           quotes: ['First quote']
         }
        },
        methods: {
          newQuote(quote) {
            if(this.quotes.length >= this.maxQuotes) {
                return alert('Please delete Quotes first')
            };
            this.quotes.push(quote);
          },
          deleteQuote(index) {
            this.quotes.splice(index, 1);
          }
        },
        components: {
            QuoteGrid,
            NewQuote,
            Header
        }
    }
</script>

<style>
</style>
