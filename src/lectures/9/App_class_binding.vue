<template>
	<div>
		<div class="text" :class="classObject">텍스트 입니다.</div>
		<button v-on:click="toggle">toggle</button>
		<button v-on:click="hasError = !hasError">toggleError</button>
	</div>
</template>

<script>
import { computed } from '@vue/reactivity';
import { reactive, ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const hasError = ref(false);
		// const classObject = reactive({
		// 	active: true,
		// 	'text-danger': false,
		// });

		const classObject = computed(() => {
			return {
				active: true && true,
				'text-danger': true && true,
			};
		});

		const activeClass = ref('active');
		const errorClass = ref('error');

		const toggle = () => {
			isActive.value = !isActive.value;
		};
		return {
			isActive,
			hasError,
			classObject,
			toggle,
			activeClass,
			errorClass,
		};
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
}

.text-danger {
	color: red;
}
</style>
