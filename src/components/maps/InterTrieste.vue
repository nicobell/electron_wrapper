<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
			<li @click="this.updateActiveIndex(2)">Item 3</li>
			<li @click="this.updateActiveIndex(3)">Item 4</li>
		</ul>
		<img src="../../assets/mappe/trieste-freeste-inland.png" alt="">
	</div>
</template>

<script>
export default {
    name: 'InterTrieste',
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
li:nth-child(1) {
	left: 66.54%;
	top: 63.63%;
}

li:nth-child(2) {
	left: 40.36%;
	top: 65.27%;
}

li:nth-child(3) {
	left: 67.63%;
	top: 33.63%;
}

li:nth-child(4) {
	left: 56.72%;
	top: 78.90%;
}
</style>