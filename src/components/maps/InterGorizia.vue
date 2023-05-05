<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
			<li @click="this.updateActiveIndex(2)">Item 3</li>
			<li @click="this.updateActiveIndex(3)">Item 4</li>
			<li @click="this.updateActiveIndex(4)">Item 5</li>
		</ul>
		<img src="../../assets/mappe/gorizia.png" alt="">

		<button class="prev-spot" @click="this.prevSpot"></button>
		<button class="next-spot" @click="this.nextSpot"></button>
	</div>
</template>

<script>
export default {
    name: 'InterGorizia',
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
	left: 30.18%;
	top: 63.27%;
}

li:nth-child(2) {

	left: 74.18%;
	top: 38.90%;
	
}

li:nth-child(3) {
	left: 10%;
	top: 60.18%;
}

li:nth-child(4) {

	left: 13.63%;
	top: 55.81%;
}

li:nth-child(5) {

	left: 63.63%;
	top: 42.72%;
	
}
</style>