<template>
	<div class="my-profile">
		<div class="item profile-photo" @click="onChooseImage">
			<div class="label">Profile Photo</div>
			<div class="value">
				<img v-if="profilePhoto" :src="profilePhoto" alt="" />
				<i class="iconfont icon-right"></i>
			</div>
		</div>
		<div class="item">
			<div class="label">Name</div>
			<div class="value">
				<text>Zoey</text>
				<i class="iconfont icon-right"></i>
			</div>
		</div>
		<div class="item">
			<div class="label">Tickle</div>
			<div class="value">
				<i class="iconfont icon-right"></i>
			</div>
		</div>
		<div class="item">
			<div class="label">Weixin ID</div>
			<div class="value">
				<text>iszhounie</text>
				<i class="iconfont icon-right"></i>
			</div>
		</div>
		<div class="item">
			<div class="label">My QR Code</div>
			<div class="value">
				<i class="iconfont icon-qr_code_light" style="font-size: 20px;"></i>
				<i class="iconfont icon-right"></i>
			</div>
		</div>
		<div class="item">
			<div class="label">More Info</div>
			<div class="value">
				<i class="iconfont icon-right"></i>
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref } from 'vue'
	const profilePhoto = ref('')
	const onChooseImage = () => {
		uni.chooseImage({
			count: 1,
			success(res) {
				console.log(res)
				uni.getImageInfo({
					src: res.tempFilePaths[0],
					success(img) {
						profilePhoto.value = img.path
					}
				})
			}
		})
	}
</script>

<style lang="scss" scoped>
	.my-profile {
		.item {
			display: flex;
			justify-content: space-between;
			align-items: center;
			background: #fff;
			padding: 12px;
			border-bottom: 1px solid #f1f1f1;
			.value {
				display: flex;
				align-items: center;
				grid-gap: 10px;
				font-size: 14px;
				color: #4D4D4D;
			}
			.icon-right {
				color: #aaa;
			}
		}
		.item:active {
			background: #f9f9f9;
		}
		.profile-photo {
			.value img {
				width: 60px;
				height: 60px;
				object-fit: cover;
				border-radius: 10px;
			}
		}
	}
</style>