<template>
	<div class="contacts">
		<div class="contacts-box">
			<div class="contacts-item" id="A">
				<div class="contacts-classify">A</div>
				<div class="friends">
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
				</div>
			</div>
			<div class="contacts-item" id="B">
				<div class="contacts-classify">B</div>
				<div class="friends">
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
				</div>
			</div>
			<div class="contacts-item">
				<div class="contacts-classify">C</div>
				<div class="friends">
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
				</div>
			</div>
			<div class="contacts-item">
				<div class="contacts-classify">D</div>
				<div class="friends">
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
					<div class="friends-item" @click="onGoFriendProfile">
						<div class="profile-photo">
							<img src="/static/wxlogo.png" alt="" />
						</div>
						<div class="friend-name">你好</div>
					</div>
				</div>
			</div>
		</div>
		<div class="classify">
			<div
				v-for="(item) in classify"
				class="classify-item" @mousemove="onSelectClassify(item)">
			<a :href="`#${item}`">{{item}}</a>	
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref } from 'vue'
	const current = ref()
	const classify = [
		'☆',
		'A',
		'B',
		'C',
		'D',
		'E',
		'F',
		'G',
		'H',
		'I',
		'J',
		'K',
		'L',
		'M',
		'N',
		'O',
		'P',
		'Q',
		'R',
		'S',
		'T',
		'U',
		'V',
		'W',
		'X',
		'Y',
		'Z',
		'#',
	]
	const onGoFriendProfile = () => {
		uni.navigateTo({
			url: '/pages/friendProfile/index'
		})
	}
	const onSelectClassify = (classify) => {
		// window.location.hash = classify
	}
</script>

<style lang="scss" scoped>
	.contacts {
		.contacts-box {
			overflow: hidden;
			.contacts-classify {
				padding: 10px;
				font-size: 12px;
			}
			.friends {
				background-color: #fff;
				.friends-item {
					display: grid;
					grid-template-columns: 50px 1fr;
					align-items: center;
					height: 50px;
					.profile-photo {
						width: 50px;
						height: 50px;
						padding: 10px;
						border-radius: 10px;
						box-sizing: border-box;
						img {
							width: 100%;
						}
					}
					.friend-name {
						line-height: 50px;
						border-bottom: 1px solid #f1f1f1;
					}
				}
				.friends-item:active {
					background: #f9f9f9;
				}
			}
		}
		.classify {
			position: fixed;
			right: 6px;
			top: 50%;
			transform: translateY(-50%);
			display: flex;
			flex-direction: column;
			grid-gap: 4px;
			align-items: center;
			.classify-item {
				font-size: 12px;
			}
		}
	}
</style>