<template>
	<div class="enter-message">
		<input :value="value" @input="onInput" />
	</div>
</template>

<script setup>
	import { ref } from 'vue'
	
	const value = ref('')
	
	const onInput = (e) => {
		value.value = e.detail.value
	}
</script>

<style lang="scss" scoped>
	.enter-message {
		background: #F1F1F1;
		padding: 6px;
		input {	
			background: #fff;
			padding: 4px;
			border-radius: 4px;
			caret-color: #1AAD19;
		}
	}
</style>