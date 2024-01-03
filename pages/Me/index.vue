<template>
	<div class="me">
		<div class="mine" @click="onGoProfile">
			<div class="left">
				<img src="/static/wxlogo.png" alt="">
			</div>
			<div class="right">
				<div class="name">Zoey</div>
				<div class="id">
					<div class="weixid">Weixin ID: iszhounie</div>
					<div class="qrcode">
						<i class="iconfont icon-qr_code_light"></i>
						<i class="iconfont icon-right"></i>
					</div>
				</div>
			</div>
		</div>
		<div class="services item">
			<view class="left">
				<i class="iconfont icon-weixinzhifu"></i>
				<text>Services</text>
			</view>
			<view class="right">
				<i class="iconfont icon-right"></i>
			</view>
		</div>
		<div class="more">
			<div class="item">
				<view class="left">
					<i class="iconfont icon-form_light" style="color: #EA6853;"></i>
					<text>Favorites</text>
				</view>
				<view class="right">
					<i class="iconfont icon-right"></i>
				</view>
			</div>
			<div class="item">
				<view class="left">
					<i class="iconfont icon-pic" style="color: #2782D7;"></i>
					<text>My Posts</text>
				</view>
				<view class="right">
					<i class="iconfont icon-right"></i>
				</view>
			</div>
			<div class="item">
				<view class="left">
					<i class="iconfont icon-vipcard" style="color: #10AEFF;"></i>
					<text>Cards & Offers</text>
				</view>
				<view class="right">
					<i class="iconfont icon-right"></i>
				</view>
			</div>
			<div class="item">
				<view class="left">
					<i class="iconfont icon-emoji" style="color: #FFBE00;"></i>
					<text>Sticker Gallery</text>
				</view>
				<view class="right">
					<i class="iconfont icon-right"></i>
				</view>
			</div>
		</div>
		<div class="setting item">
			<view class="left">
				<i class="iconfont icon-settings_light"></i>
				<text>Settings</text>
			</view>
			<view class="right">
				<i class="iconfont icon-right"></i>
			</view>
		</div>
	</div>
</template>

<script setup>
	const onGoProfile = () => {
		uni.navigateTo({
			url: '/pages/myProfile/index'
		})
	}
</script>

<style lang="scss" scoped>
	.me {
		display: flex;
		flex-direction: column;
		grid-gap: 10px;
		.mine {
			background: #fff;
			display: flex;
			grid-gap: 14px;
			padding: 20px;
			padding-top: 0;
			.left {
				width: 60px;
				height: 60px;
				img {
					width: 100%;
				}
			}
			.right {
				flex: 1;
				.name {
					font-size: 16px;
					font-weight: 600;
					padding-bottom: 10px;
				}
				.id {
					display: flex;
					justify-content: space-between;
					align-items: center;
					.weixid {
						font-size: 12px;
					}
					.qrcode {
						display: flex;
						align-items: center;
						grid-gap: 20px;
					}
				}
			}
		}
		.item {
			background: #fff;
			padding: 12px;
			box-sizing: border-box;
			display: flex;
			justify-content: space-between;
			align-items: center;
			.left {
				display: flex;
				align-items: center;
				grid-gap: 14px;
				.iconfont {
					font-size: 24px;
					color: #1AAD19;
				}
			}
			.right {
				.iconfont {
					font-size: 18px;
					color: #AAAAAA;
				}
			}
		}
		.item:active {
			background: #f9f9f9;
		}
		.setting {
			.left {
				.iconfont {
					color: #2782D7;
				}
			}
		}
		.more {
			.item:not(:last-child) {
				border-bottom: 1px solid #f1f1f1;
			}
		}
	}
</style>