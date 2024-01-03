<template>
	<div>
		<div class="item" @click="onClickItem">
			<div class="profile">
				<img src="/static/wxlogo.png" alt="" />
			</div>
			<div class="item-message">
				<div class="item-message-head">
					<div class="name">美团</div>
					<div class="time">3:22PM</div>
				</div>
				<div class="message">
					两个加拉国家二级过了安检过了啊攻击力两个加拉国家二级过了安检过了啊攻击力
				</div>
			</div>
		</div>
		<div class="item" @click="onClickItem">
			<div class="profile">
				<img src="/static/wxlogo.png" alt="" />
			</div>
			<div class="item-message">
				<div class="item-message-head">
					<div class="name">美团</div>
					<div class="time">3:22PM</div>
				</div>
				<div class="message">
					两个加拉国家二级过了安检过了啊攻击力
				</div>
			</div>
		</div>
		<div class="item" @click="onClickItem">
			<div class="profile">
				<img src="/static/wxlogo.png" alt="" />
			</div>
			<div class="item-message">
				<div class="item-message-head">
					<div class="name">美团</div>
					<div class="time">3:22PM</div>
				</div>
				<div class="message">
					两个加拉国家二级过了安检过了啊攻击力
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref } from 'vue'
	
	const a = ref()
	
	const onClickItem = () => {
		uni.navigateTo({
			url: '/pages/Chat/index',
			fail: (err) => {
				console.log(err)
			}
		});
		
	}
</script>

<style lang="scss">
	.item {
		display: flex;
		.profile {
			width: 60px;
			padding: 10px;
			box-sizing: border-box;
			img {
				width: 100%;
			}
		}
		.item-message {
			flex: 1;
			border-bottom: 1px solid #ccc;
			box-sizing: border-box;
			padding: 10px;
			padding-left: 0;
			.item-message-head {
				display: flex;
				justify-content: space-between;
				padding-bottom: 4px;
				box-sizing: border-box;
				.name {
					font-size: 16px;
					font-weight: 600;
				}
				.time {
					font-size: 12px;
					color: #aaa;
				}
			}
			.message {
				width: 250px;
				font-size: 12px;
				color: #aaa;
				overflow: hidden;
				text-overflow: ellipsis;
				white-space: nowrap;
			}
		}
	}
</style>