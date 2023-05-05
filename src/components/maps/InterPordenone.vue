<template>
	<div class="videomap container">
		<ul id="list">
			<li @click="this.updateActiveIndex(0)" class="active">Item 1</li>
			<li @click="this.updateActiveIndex(1)">Item 2</li>
			<li @click="this.updateActiveIndex(2)">Item 3</li>
			<li @click="this.updateActiveIndex(3)">Item 4</li>
			<li @click="this.updateActiveIndex(4)">Item 5</li>
		</ul>
		<img src="../../assets/mappe/pordenone.png" alt="">

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
    left: 7.27%;
    top: 25.45%;
}

li:nth-child(2) {
    left: 32.72%;
    top: 22.09%;
}

li:nth-child(3) {
    left: 79.99%;
    top: 26.72%;
}

li:nth-child(4) {
    left: 29.09%;
    top: 49.27%;
}

li:nth-child(5) {
    left: 41.45%;
    top: 35.45%;
}
</style>