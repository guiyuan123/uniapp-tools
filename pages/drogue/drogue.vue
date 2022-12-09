<template>
	<view class="container" @touchmove="handleScroll">
		<view>

		</view>
		<view class="drogue" :class="{ 'close': isClose }">
			<DrogueItem iconType="primary">开门</DrogueItem>
			<DrogueItem iconType="info">续单</DrogueItem>
			<DrogueItem iconType="danger">离店</DrogueItem>
		</view>
	</view>
</template>

<script>
	import DrogueItem from '@/components/Drogue/DrogueItem.vue'

	export default {
		components: {
			DrogueItem
		},
		data() {
			return {
				delay: 1500,
				isClose: false,
				timer: null
			};
		},
		methods: {
			handleScroll() {
				this.isClose = true
				this.destroyScroll()
				this.timer = setTimeout(() => {
					this.isClose = false
				}, this.delay)
			},
			destroyScroll() {
				clearTimeout(this.timer)
				this.timer = null
			}
		}
	}
</script>

<style>
	.container {
		height: 3000px;
		width: 100%;
		background-color: #9e9e9e;
	}

	.drogue {
		position: fixed;
		right: 0;
		bottom: 50px;
		padding: 20px 10px;
		display: flex;
		flex-direction: column;
		gap: 8px;
		-webkit-transition: transform 0.3s;
		transition: transform 0.3s;
	}

	.close {
		-webkit-transform: translateX(650%);
		transform: translateX(65%);
	}
</style>
