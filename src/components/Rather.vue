<template>
	<div class="would-you-rather">
		<h1>Would you rather...</h1>
	
		<h2>{{ questions }}</h2>
		<input type="radio" v-model="selection" v-bind:value="answer1">
		{{answer1}}
		<input type="radio" v-model="selection" v-bind:value="answer2">
		{{answer2}}
    </div>
</template>

<script>
export default {
	name: 'Rather',
	props: {
		questions: String,
		answer1: String,
		answer2: String
	},
	data() {
		return {
			selection: ''
		}
	},
	watch: {
		selection() {
			this.$emit('selection-changed', this.selection, this.id)
		}
	}
}


</script>

<style>
	.would-you-rather{
        display: block;
        padding:5px;
        background-image: linear-gradient( rgb(240, 232, 250), rgb(204, 124, 241));
        margin-bottom: 10px;
    }
</style>
