<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon">&#xe624;</div>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
			输入城市/景点/游玩主题
		</div>
		<router-link to="/city">
			<div class="header-right">
				{{ this.city }}
				<span class="iconfont down-icon">&#xe843;</span>
			</div>
		</router-link>
	</div>
</template>

<script>
export default {
	name: 'HomeHeader',
	props: {
		city: String
	}
}
</script>

<style lang="less" scoped>
.header {
	display: flex;
	line-height: .86rem;
	background: #00bcd4;
	color: #fff;

	.header-left {
		width: .64rem;
		float: left;

		.back-icon {
			font-size: .4rem;
			text-align: center;
		}
	}

	.header-input {
		flex: 1;
		background: #fff;
		padding-left: .2rem;
		line-height: .64rem;
		color: #ccc;
		height: .64rem;
		margin-top: .12rem;
		margin-left: .2rem;
		border-radius: .1rem;
	}

	.header-right {
		width: 1.24rem;
		float: right;
		text-align: center;

		.down-icon {
			margin-left: -.05rem;
			font-size: .25rem;
		}
	}
}
</style>
