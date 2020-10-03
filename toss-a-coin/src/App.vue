<template>
	<div id="app">
		<div class="coin">{{ coins }}</div>
		<button v-on:click="tossACoin">Toss</button>
		<button v-on:click="addCoin">Add coin</button>
		<button v-on:click="removeCoin">removeCoin</button>
	</div>
</template>

<script>
export default {
	name: 'App',
	data() {
		return { 
			numberOfCoin: 1,
			coinStatus: ['H'] 
		};
	},
	computed: {
		coins() {
			return this.coinStatus.join();
		}
	},
	methods: {
		addCoin() {
			this.numberOfCoin += 1;
			this.coinStatus.push('H');
		},
		removeCoin() {
			this.numberOfCoin -= 1;
			this.coinStatus.pop();
		},
		tossACoin() {
			const hOrT = 'HT';
			this.coinStatus = this.coinStatus.map(() => hOrT[Math.floor(Math.random() * 2)]);
		},
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
