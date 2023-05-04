<template>
	<div class="videomap container">
		<ul id="list">
			<li class="active">Item 1</li>
			<li>Item 2</li>
			<li>Item 3</li>
			<li>Item 4</li>
			<li>Item 4</li>
		</ul>
		<img src="../../assets/mappe/pordenone.png" alt="">
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