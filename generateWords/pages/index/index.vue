<template>
	<view class="content">
		<view class="button">
			<view class="button1">
				<button @click="oneWord()">生成一次</button>
			</view>
			<view class="button2">
				<button @click="tenWords()">生成十次</button>
			</view>
		</view>
		<view class="text-area">
			<view class="text" v-for="(item,index) in wordsArray" :key="index">
				<li>{{item}}</li>
				<view class="divider" />
			</view>
		</view>
	</view>
</template>

<script>
	import {
		words
	} from './words.js'
	export default {
		data() {
			return {
				wordsArray: ['']
			}
		},


		created() {

		},
		methods: {
			randNum() {
				return Math.round(Math.random() * 3500);
			},
			chooseWord() {
				return words[this.randNum()] + words[this.randNum()]
			},
			oneWord() {
				this.wordsArray = [];
				this.wordsArray.push(this.chooseWord());
			},
			tenWords() {
				this.wordsArray = [];
				for (let i = 0; i < 10; i++) {
					this.wordsArray.push(this.chooseWord());
				}
			}
		},
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		width: 100%;
		justify-content: center;
		font-size: 1.3rem;
	}

	.text {
		width: 100%;
		text-align: center;
	}

	.title {
		font-size: 36rpx;
		color: black;
	}

	.button {
		line-height: 38px;
		text-align: center;
		font-weight: bold;
		color: #fff;
		border-radius: 5px;
		margin: 30px auto;
		display: flex;


	}

	.button1 {
		float: left;
		padding-right: 30px;
	}

	.button2 {
		float: right;
	}


	.divider {
		background: #E0E3DA;
		width: 100%;
		height: 5rpx;
		margin-top: 2px;
		margin-bottom: 5px;
	}
</style>