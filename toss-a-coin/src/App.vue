<template>
	<div id="app">
		<div class="coins">
			<div
				class="coin"
				v-for="(coin, index) in coinStatus"
				:key="index"
			>
				<p>{{ coin }}</p>
			</div>
		</div>
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
			coinStatus: ['H'],
		};
	},
	computed: {
		coins() {
			return this.coinStatus.join();
		},
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
			this.coinStatus = this.coinStatus.map(
				() => hOrT[Math.floor(Math.random() * 2)]
			);
		},
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	color: #2c3e50;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}

.coin {
	display: flex;
	justify-content: center;
	align-items: center;
	margin: 0.2rem;
	width: 2rem;
	height: 2rem;
	border-radius: 50%;
	background-color: rgb(238, 188, 25);
}

.coin p {
	color: whitesmoke;
	font-weight: bold;
}

.coins {
	display: flex;
	margin: 1rem;
}
</style>
