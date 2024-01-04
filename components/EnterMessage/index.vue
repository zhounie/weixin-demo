<template>
	<div class="enter-message">
		<input :value="value" @input="onInput" @keydown.enter="onEnter" />
	</div>
</template>

<script setup>
	import { ref, defineEmits } from 'vue'
	
	const emit = defineEmits(['send'])
	
	const value = ref('')
	
	const onInput = (e) => {
		value.value = e.detail.value
	}
	
	const onEnter = () => {
		emit('send', value.value)
		value.value = ''
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