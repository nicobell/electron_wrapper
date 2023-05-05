<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
			<li @click="this.updateActiveIndex(2)">Item 3</li>
			<li @click="this.updateActiveIndex(3)">Item 4</li>
			<li @click="this.updateActiveIndex(4)">Item 5</li>
			<li @click="this.updateActiveIndex(5)">Item 6</li>
		</ul>
		<img src="../../assets/mappe/nogaro.png" alt="">

		<button class="prev-spot" @click="this.prevSpot"></button>
		<button class="next-spot" @click="this.nextSpot"></button>
	</div>
</template>

<script>
export default {
    name: 'PortoNogaro',
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

			//console.log(this.activeIndex, listItems[index])
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
	left: 45.63%;
	top: 41.81%;
}

li:nth-child(2) {
	left: 41.99%;
	top: 52.72%;
}

li:nth-child(3) {
	left: 41.27%;
	top: 74.54%;
}

li:nth-child(4) {
	left: 50.36%;
	top: 74.54%;
}

li:nth-child(5) {
	left: 24.18%;
	top: 31.63%;
}

li:nth-child(6) {
	left: 33.27%;
	top: 14.54%;
}
</style>