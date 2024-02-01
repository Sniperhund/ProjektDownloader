<script setup lang="ts">
const props = defineProps({
	number: {
		type: String,
		required: true,
	},
	selected: {
		type: Boolean,
		default: false,
	},
});
</script>

<template>
	<NuxtLink :to="'/week/' + number">
		<li :class="selected == true ? 'selected' : ''">
			<div>
				<p>Uge</p>
				<h2>{{ props.number }}</h2>
			</div>
			<NuxtImg :src="'/imgs/' + number + '.jpg'" />

			<h3>Lorem Ipsum</h3>
		</li>
	</NuxtLink>
</template>

<style scoped>
.selected {
	background-color: white;
	box-shadow: -14px 10px 26px -6px rgba(0, 0, 0, 0.19);
	border-radius: 1rem;
}

@media screen and (max-width: 768px) {
	.selected {
		border-radius: 0;
	}
}

li {
	display: flex;
	align-items: center;
	max-height: 150px;
	gap: 2rem;
	padding: 1rem 2rem;
	cursor: pointer;
}

div {
	text-align: center;
}

img {
	border-radius: 1rem;
	aspect-ratio: 1.5 / 1;
	max-height: 100px;
	max-width: 150px;
}

p {
	font-size: 0.8rem;
	color: #a5a5a5;
}

h2 {
	font-size: 2rem;
	color: #000;
}

h3 {
	text-overflow: ellipsis;
	font-size: 1.2rem;
	font-weight: 500;
}
</style>
