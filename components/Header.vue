<script setup lang="ts">
const props = defineProps({
	img: {
		type: String,
		required: true,
	},
});

const route = useRoute();

function getIfSelected(index: number) {
	let week = route.fullPath.split("/")[2];
	return week == index.toString();
}
</script>

<template>
	<ul>
		<HeaderCard
			v-for="i in 2"
			:number="i.toString()"
			:selected="getIfSelected(i)"
		/>
	</ul>
</template>

<style scoped>
ul {
	display: flex;
	flex-direction: column;
	gap: 2px;
	border-radius: 1rem 1rem 0 0;
	width: 40%;
	background-color: #f9f9fb;
	padding: 1.5rem 2rem;
}
</style>
