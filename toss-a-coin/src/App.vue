<template>
	<div id="app">
		<div class="coin">{{ coinStatus }}</div>
    <button @click="tossACoin">Toss</button>
	</div>
</template>

<script>
export default {
	name: 'App',
	data() {
		return { coinStatus: 'H' };
  },
  methods: {
    tossACoin () {
      const hOrT = 'HT';
      this.coinStatus = hOrT[Math.floor(Math.random() * 2)];
    }
  }
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
