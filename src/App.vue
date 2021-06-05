<template>
    <div class="container">       
        <Header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></Header>
        <new-quote @quoteAdded="newQuote"></new-quote>
        <quote-gride :quotes="quotes" @quoteDeleted="deleteQuote"></quote-gride>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to Delete It!</div>
            </div>
        </div>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import NewQuote from './components/NewQuote.vue'
import QuoteGride from './components/QuoteGride.vue'
    export default {
        data:function(){
            return{
                quotes:['Just a Quote to see Something'],
                maxQuotes:10
            }
        },
        methods:{
            newQuote(quote){
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index,1);
            }
        },
        components: { QuoteGride, NewQuote, Header },
        
    }
</script>

<style scoped>
</style>
