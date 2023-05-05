<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
			<li @click="this.updateActiveIndex(2)">Item 3</li>
			<li @click="this.updateActiveIndex(3)">Item 4</li>
			<li @click="this.updateActiveIndex(4)">Item 5</li>
			<li @click="this.updateActiveIndex(5)">Item 6</li>
			<li @click="this.updateActiveIndex(6)">Item 7</li>
		</ul>
		<img src="../../assets/mappe/cervignano.png" alt="">

		<button class="prev-spot" @click="this.prevSpot"></button>
		<button class="next-spot" @click="this.nextSpot"></button>
	</div>
</template>

<script>
export default {
    name: 'InterCervignano',
    props: {},
    data() {
        return {
			activeIndex: 0
		}
    },
    computed: {
		numSpots() {
			return document.querySelectorAll('#list li').length;
		}
	},
    methods: {
		updateActiveIndex(index) {
			const listItems = document.querySelectorAll('#list li');

			listItems.forEach(item => item.classList.remove('active'));
			listItems[index].classList.add('active');
			
			this.activeIndex = index;

			this.$emit('update-video-index', this.activeIndex)
		},
		nextSpot() {
			if(this.activeIndex<this.numSpots-1)
				this.activeIndex += 1
			else
				this.activeIndex = 0

			this.updateActiveIndex(this.activeIndex)
		},
		prevSpot() {
			if(this.activeIndex==0)
				this.activeIndex = this.numSpots-1
			else
				this.activeIndex -= 1

			this.updateActiveIndex(this.activeIndex)
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
	left: 48.72%;
	top: 20.72%;
}

li:nth-child(3) {
	left: 51.81%;
	top: 16%
}

li:nth-child(4) {
	left: 38%;
	top: 16.18%;
}

li:nth-child(5) {
	left: 47.27%;
	top: 11.63%;
}

li:nth-child(6) {
	left: 33.45%;
	top: 8%;
}

li:nth-child(7) {
	left: 41.45%;
	top: 65.45%;
}
</style>