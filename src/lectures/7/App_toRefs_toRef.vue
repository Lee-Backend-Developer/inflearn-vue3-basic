<template>
	<div>
		<p>author: {{ author }}</p>
		<p>title: {{ title }}</p>
	</div>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2020',
			title: 'Vue 3 Guide',
			description: '당신은 이 책을 지금 바로 읽습니다 ;)',
			price: '무료',
		});

		let { author, title } = book;
		return {
			author,
			title,
		};
	},
};
</script>

<style lang="scss" scoped></style>
