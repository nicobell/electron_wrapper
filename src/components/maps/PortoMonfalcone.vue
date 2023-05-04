<template>
	<div class="videomap container">
		<ul id="list">
			<li class="active">Item 1</li>
			<li>Item 2</li>
			<li>Item 3</li>
			<li>Item 4</li>
			<li>Item 5</li>
			<li>Item 6</li>
			<li>Item 7</li>
			<li>Item 8</li>
			<li>Item 9</li>
			<li>Item 10</li>
		</ul>
		<img src="../../assets/mappe/monfalcone.png" alt="">
	</div>
</template>

<script>
export default {
    name: 'InterPordenone',
    props: {},
    data() {
        return {}
    },
    computed: {},
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
	left: 7.8%;
    top: 27.27%;
}
li:nth-child(2) {     
	left: 18.18%;
    top: 43.63%;
}
li:nth-child(3) {     
	left: 25.99%;
    top: 45.99%;
}
li:nth-child(4) {     
	left: 29.81%;
    top: 38.18%;
}
li:nth-child(5) {     
	left: 27.09%;
    top: 58.18%;
}
li:nth-child(6) {     
	left: 34.36%;
    top: 43.99%;
}
li:nth-child(7) {     
	left: 69.09%;
    top: 72.72%;
}
li:nth-child(8) {         
	left: 50.90%;
    top: 61.81%;
}
li:nth-child(9) {     
	left: 10.90%;
    top: 34.54%;
}
li:nth-child(10) { 
	left: 69.09%;
    top: 58.18%;
}
</style>