<template>
	<view class="drogue-item" :class="iconType">
		<icon></icon>
		<view>
			<slot></slot>
		</view>
	</view>
</template>

<script>
	export default {
		name: "DrogueItem",
		props: {
			iconType: {
				type: String,
				default: 'primary' // primary、info、danger
			}
		}
	}
</script>

<style>
	.drogue-item {
		width: 50px;
		height: 50px;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 50%;
		font-size: 12px;
	}

	.drogue-item.primary {
		background-color: rgb(80, 133, 212);
		color: #fff;
	}

	.drogue-item.info {
		background-color: #fff;
		color: rgb(80, 133, 212);
	}

	.drogue-item.danger {
		background-color: #fff;
		color: rgb(214, 70, 89);
	}
</style>
