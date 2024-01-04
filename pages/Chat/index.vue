<template>
	<view class="chat">
		<view class="chat-box">
			<scroll-view
				class="chat-box-scroll"
				:scroll-y="true"
				:show-scrollbar="false"
				:scroll-into-view="scrollIntoView"
			>
				<view class="chat-item">
					<view class="profile-photo">
						<img src="/static/wxlogo.png" alt="">
					</view>
					<view class="message-box">
						<view class="message">你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你</view>
					</view>
				</view>
				<view class="chat-item">
					<view class="profile-photo">
						<img src="/static/wxlogo.png" alt="">
					</view>
					<view class="message-box">
						<view class="message">你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你</view>
					</view>
				</view>
				<view class="chat-item me">
					<view class="profile-photo">
						<img src="/static/wxlogo.png" alt="">
					</view>
					<view class="message-box">
						<view class="message">你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你</view>
					</view>
				</view>
				<view class="chat-item me">
					<view class="profile-photo">
						<img src="/static/wxlogo.png" alt="">
					</view>
					<view class="message-box">
						<view class="message">你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你</view>
					</view>
				</view>
				<view class="chat-item me">
					<view class="profile-photo">
						<img src="/static/wxlogo.png" alt="">
					</view>
					<view class="message-box">
						<view class="message">你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你</view>
					</view>
				</view>
				<view class="chat-item">
					<view class="profile-photo">
						<img src="/static/wxlogo.png" alt="">
					</view>
					<view class="message-box">
						<view class="message">你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你你好你好你好你好你</view>
					</view>
				</view>
				<view v-for="(item, index) in chatList" :class="{
					'chat-item': true,
					'me': item.origin === 'me'
				}" :key="index" :id="`chat-${index}`">
					<view class="profile-photo">
						<img src="/static/wxlogo.png" alt="">
					</view>
					<view class="message-box">
						<view class="message">{{item.value}}</view>
					</view>
				</view>
			</scroll-view>
		</view>
		<EnterMessage @send="onSend" />
	</view>
</template>

<script setup>
	import { ref, onMounted, nextTick } from 'vue'
	import EnterMessage from '../../components/EnterMessage/index.vue'
	
	const chatList = ref([])
	
	
	const scrollIntoView = ref('')
	
	const onSend = (message) => {
		chatList.value.push({
			type: 'text',
			origin: 'me',
			value: message
		})
		nextTick(() => {
			scrollIntoView.value = `chat-${chatList.value.length - 1}`
		})
	}
	
	onMounted(() => {
		uni.setNavigationBarTitle({
			title: '新的标题'
		});
	})
</script>

<style lang="scss" scoped>
	.chat {
		display: flex;
		flex-direction: column;
		height: calc(100vh - 44px);
		box-sizing: border-box;
		.chat-box {
			flex: 1;
			overflow: hidden;
			padding: 10px;
			box-sizing: border-box;
			.chat-box-scroll {
				height: 100%;
			}
			.chat-item {
				display: flex;
				grid-gap: 10px;
				margin-bottom: 10px;
				.profile-photo {
					width: 40px;
					height: 40px;
					img {
						width: 100%;
					}
				}
				.message-box {
					flex: 1;
					box-sizing: border-box;
					.message {
						display: inline-block;
						border-radius: 5px;
						background: #fff;
						padding: 10px;
						line-height: 20px;
						position: relative;
					}
				}
			}
			.chat-item:not(.me) {
				.message::before {
					content: '';
					position: absolute;
					left: -6px;
					top: 14px;
					display: block;
					width: 0;
					height: 0;
					border-top: 6px solid transparent;
					border-bottom: 6px solid transparent;
					border-right: 6px solid #fff;
					// transform: rotate(-90deg);
				}
			}
			.chat-item.me {
				.profile-photo {
					order: 2;
				}
				.message-box {
					order: 1;
					.message {
						float: right;
						background: #91ED61;
					}
					.message::after {
						content: '';
						position: absolute;
						right: -6px;
						top: 14px;
						display: block;
						width: 0;
						height: 0;
						border-top: 6px solid transparent;
						border-bottom: 6px solid transparent;
						border-left: 6px solid #91ED61;
						// transform: rotate(-90deg);
					}
				}
			}
		}
	}
</style>