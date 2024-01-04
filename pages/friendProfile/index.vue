<template>
	<view class="friend-profile">
		<view class="profile">
			<view class="profile-photo">
				<img src="/static/wxlogo.png" alt="" />
			</view>
			<view class="profile-info">
				<view class="nickname">
					Zoey
				</view>
				<view class="name">
					Name: zn
				</view>
				<view class="weixinid">
					Weixin ID: 352352352
				</view>
				<view class="region">
					Region: Jiangxi SR
				</view>
			</view>
		</view>
		<view class="">
			<Cell label="Moments" @click="onGoMoments" />
			<Cell label="More" />
		</view>
		<view class="chat">
			<view class="chat-item" @click="onGoChat">
				<i class="iconfont icon-video"></i>
				Send Message</view>
			<view class="chat-item">
				<i class="iconfont icon-message_light"></i>
				Voice or Video Call</view>
		</view>
	</view>
</template>

<script setup>
	import Cell from '../../components/Cell/index.vue'
	const onGoChat = () =>{
		uni.navigateTo({
			url: '/pages/Chat/index'
		})
	}
	const onGoMoments = () =>{
		uni.navigateTo({
			url: '/pages/moments/index'
		})
	}
</script>

<style lang="scss" scoped>
	.friend-profile {
		display: flex;
		flex-direction: column;
		grid-gap: 10px;
		.profile {
			display: flex;
			grid-gap: 18px;
			padding: 14px;
			background-color: #fff;
			.profile-photo {
				width: 50px;
				height: 50px;
				img {
					width: 100%;
				}
			}
			.profile-info {
				font-size: 14px;
				font-weight: 300;
			}
			.nickname {
				font-size: 18px;
				font-weight: 600;
				padding-bottom: 6px;
			}
		}
	}
	.chat {
		background-color: #fff;
		.chat-item {
			height: 50px;
			display: flex;
			align-items: center;
			justify-content: center;
			grid-gap: 10px;
			color: #2782D7;
			border-bottom: 1px solid #f1f1f1;
			.iconfont {
				color: #2782D7;
				font-size: 20px;
			}
		}
		.chat-item:active {
			background: #f9f9f9;
		}
	}
</style>