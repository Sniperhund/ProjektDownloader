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
	<li :class="selected == true ? 'selected' : ''">
		<NuxtLink :to="'/week/' + number">
			<div>
				<p>Uge</p>
				<h2>{{ props.number }}</h2>
			</div>
			<figure>
				<NuxtImg :src="'/imgs/' + number + '.jpg'" />
			</figure>

			<h3>Lorem Ipsum</h3>
		</NuxtLink>
	</li>
</template>

<style scoped>
.selected {
	background-color: white;
	box-shadow: -14px 10px 26px -6px rgba(0, 0, 0, 0.19);
	border-radius: 1rem;
}

@media screen and (max-width: 1023px) {
	.selected {
		border-radius: 0;
	}
}

li {
	max-height: 150px;
	padding: 1rem 2rem;
	cursor: pointer;
}

a {
	display: flex;
	align-items: center;
	gap: 2rem;
}

div {
	text-align: center;
	flex: 1 1 10%;
}

figure {
	flex: 1 1 40%;
	max-width: 150px;
}

img {
	border-radius: 1rem;
	aspect-ratio: 1.5 / 1;
	width: 100%;
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
	flex: 1 1 30%;
}
</style>
