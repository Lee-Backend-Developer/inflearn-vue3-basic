<template>
	<div>
		<h2>반응형 메시지</h2>
		<p>{{ reactiveMessage }}</p>
		<button v-on:click="addReactiveMessage">Add Message</button>
		<h2>일반 메시지</h2>
		<p>{{ normaMessage }}</p>
		<button v-on:click="addNormalMessage">Add Message</button>
	</div>
</template>

<script>
import { ref, isRef, onMounted, onBeforeMount } from 'vue';

export default {
	setup() {
		console.log('setup()');
		const reactiveMessage = ref('Hello Reactive Message');
		const addReactiveMessage = () => {
			reactiveMessage.value = reactiveMessage.value + '!';
		};
		console.log('isRef(reactiveMessage): ', isRef(reactiveMessage));

		let normaMessage = 'Hello Normal Message';
		const addNormalMessage = () => {
			normaMessage = normaMessage + '!';
		};
		console.log('isRef(normaMessage): ', isRef(normaMessage));

		onMounted(() => {
			console.log('onMounted');
		});
		onBeforeMount(() => {
			console.log('onBeforeMount');
		});

		return {
			reactiveMessage,
			normaMessage,
			addReactiveMessage,
			addNormalMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
