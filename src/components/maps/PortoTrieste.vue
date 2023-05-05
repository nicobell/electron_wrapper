<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
			<li @click="this.updateActiveIndex(2)">Item 3</li>
			<li @click="this.updateActiveIndex(3)">Item 4</li>
		</ul>
		<img src="../../assets/mappe/trieste-porto.jpg" alt="">

		<button class="prev-spot" @click="this.prevSpot"></button>
		<button class="next-spot" @click="this.nextSpot"></button>
	</div>
</template>

<script>
export default {
    name: 'PortoTrieste',
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
	left: 58%;
	top: 66%;
}

li:nth-child(2) {
	left: 67.81%;
	top: 68%;
}

li:nth-child(3) {
	left: 59.81%;
	top: 58.90%;
}

li:nth-child(4) {
	left: 63.27%;
	top: 51.63%;
}
</style>