<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
		</ul>
		<img src="../../assets/mappe/monfalcone.png" alt="">

		<button class="prev-spot" @click="this.prevSpot"></button>
		<button class="next-spot" @click="this.nextSpot"></button>
	</div>
</template>

<script>
export default {
    name: 'InterPordenone',
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
	left: 18.18%;
	top: 43.63%;
}

li:nth-child(2) {
	left: 29.81%;
	top: 38.18%;
}
</style>