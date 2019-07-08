<template>
	<div class="row">
		<Quote v-for="(quote, index) in quotesArray" @click.native="deleteQuote(index)">{{ quote }}</Quote>
	</div>
</template>

<script>
	import Quote from "./Quote.vue";

	export default {
		components: {
			Quote
		},
		name: "QuoteGrid",
		props: ['quotesArray'],
		methods: {
			deleteQuote(index) {
				this.$emit('quoteDeleted', index);
			}
		}
	}
</script>

<style scoped>

</style>