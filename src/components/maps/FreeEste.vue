<template>
	<div class="videomap container">
		<ul id="list">
			<li style="display: none;">hidden</li>
			<li style="display: none;">hidden</li>
			<li style="display: none;">hidden</li>
			<li style="display: none;">hidden</li>
			<li @click="this.updateActiveIndex(0)">Item 5</li>
			<li @click="this.updateActiveIndex(1)">Item 6</li>
			<li @click="this.updateActiveIndex(2)">Item 7</li>
			<li @click="this.updateActiveIndex(3)">Item 8</li>
		</ul>
		<img src="../../assets/mappe/trieste-freeste-terminal.png" alt="">
	</div>
</template>

<script>
export default {
    name: 'FreeEste',
    props: {},
    data() {
        return {}
    },
    computed: {},
    methods: {
		updateActiveIndex(index) {
			const listItems = document.querySelectorAll('#list li');

			listItems.forEach(item => item.classList.remove('active'));
			listItems[index].classList.add('active');
			
			this.activeIndex = index;

			this.$emit('update-video-index', this.activeIndex)
		}
	},
    mounted() {}
}
</script>

<style scoped>
li:nth-child(5) {
	left: 34.36%;
	top: 53.45%;
}

li:nth-child(6) {
	left: 55.45%;
	top: 40.72%;
}

li:nth-child(7) {
	left: 41.99%;
	top: 42.54%;
}

li:nth-child(8) {
	left: 16.90%;
	top: 41.45%;
}
</style>