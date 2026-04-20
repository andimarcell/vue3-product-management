<script setup>
import ProductCard from '@/components/ProductCard.vue';
import Pagination from '@/components/Pagination.vue';

import { onUpdated, onBeforeMount, onBeforeUpdate, onMounted, ref } from 'vue';

const PAGE = ref(1);

function nextPage() {
	PAGE.value ++;
}

onBeforeMount(() => {
	console.log('component will be mounted');
});

onMounted(() => {
	console.log('component has been fully loaded');
});

onBeforeUpdate(() => {
	console.log('component will be updated');
});

onUpdated(() => {
	console.log('component has been updated');
});

</script>


<template>
	<main>
	{{ PAGE }}
	<button @click="nextPage">Next</button>
		<div class="product-grid">
			<ProductCard />
		</div>
		<div class="pagination">
			<Pagination />
		</div>
	</main>
</template>

<style scoped>
.product-grid {
	display: grid;
	grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
	gap: 20px;
	width: 80%;
	margin: 0 auto;
}

.pagination {
	display: flex;
	justify-content: center;
	align-items: center;
	margin-top: 20px;
}


</style>