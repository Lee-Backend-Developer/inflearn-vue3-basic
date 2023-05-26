<template>
	<div>
		<div v-memo="[subcribers, views, likes]">
			<p>subcribers: {{ subcribers }}</p>
			<p>views: {{ views }}</p>
			<p>likes: {{ likes }}</p>
		</div>
		<button @click="subcribers++">Subs++</button>
		<button @click="views++">views++</button>
		<button @click="likes++">likes++</button>
		<div>
			<p>subcribers: {{ subcribers }}</p>
			<p>views: {{ views }}</p>
			<p>likes: {{ likes }}</p>
		</div>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const subcribers = ref(4000);
		const views = ref(400);
		const likes = ref(20);
		return { subcribers, views, likes };
	},
};
</script>

<style lang="scss" scoped></style>
