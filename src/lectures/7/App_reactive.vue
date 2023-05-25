<template>
	<div>
		<button v-on:click="incremeent">Click {{ state.count }}</button>
		<button v-on:click="incremeent">Deep Click {{ state.deep.count }}</button>
	</div>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const state = reactive({
			count: 0,
			deep: {
				count: 0,
			},
		});
		const incremeent = () => {
			state.count++;
			state.deep.count++;
		};
		return {
			state,
			incremeent,
		};
	},
};
</script>

<style lang="scss" scoped></style>
