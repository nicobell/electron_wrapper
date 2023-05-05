<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
			<li @click="this.updateActiveIndex(2)" style="background-color: red;">Item 3</li>
			<li @click="this.updateActiveIndex(3)">Item 4</li>
			<li @click="this.updateActiveIndex(4)">Item 5</li>
			<li @click="this.updateActiveIndex(5)">Item 6</li>
			<li @click="this.updateActiveIndex(6)" style="background-color: red;">Item 3-2</li>
		</ul>
		<img src="../../assets/mappe/cervignano.png" alt="">
	</div>
</template>

<script>
export default {
    name: 'InterCervignano',
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
	left: 32.72%;
	top: 18.54%;
}

li:nth-child(2) {
	left: 47.27%;
	top: 18.54%;
}

li:nth-child(3) {
	left: 50.72%;
	top: 17.81%;
}

li:nth-child(4) {
	left: 37.63%;
	top: 14.18%;
}

li:nth-child(5) {
	left: 34.36%;
	top: 9.27%;
}

li:nth-child(6) {
	left: 40.72%;
	top: 66.18%;
}

li:nth-child(7) {
	left: 47.27%;
	top: 12.72%;
}
</style>