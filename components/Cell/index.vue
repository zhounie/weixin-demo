<template>
	<view class="cell">
		<view class="label">{{label}}</view>
		<i class="iconfont icon-right"></i>
	</view>
</template>

<script setup>
	import { defineProps } from 'vue'
	const props = defineProps({
		label: String
	})
</script>

<style lang="scss" scoped>
	.cell {
		background-color: #fff;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 14px;
		border-bottom: 1px solid #f1f1f1;
		.label {
			
		}
	}
	.cell:active {
		background: #f9f9f9;
	}
</style>