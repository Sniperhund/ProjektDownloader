<script setup lang="ts">
const weeks = 2;

const props = defineProps({
	img: {
		type: String,
		required: true,
	},
});

const route = useRoute();
const viewport = useViewport();

function getIfSelected(index: number) {
	let week = route.fullPath.split("/")[2];
	return week == index.toString();
}

const isMenuOpen = ref(false);
</script>

<template>
	<ul v-if="viewport.isGreaterOrEquals('tablet')">
		<HeaderCard
			v-for="i in weeks"
			:number="i.toString()"
			:selected="getIfSelected(i)"
		/>
	</ul>
	<nav v-else>
		<div>
			<h3>Projekt Downloader</h3>
			<Icon
				name="i-material-symbols-menu-rounded"
				class="icon"
				@click="isMenuOpen = !isMenuOpen"
			/>
		</div>

		<ul :class="isMenuOpen ? 'shown' : ''">
			<HeaderCard
				v-for="i in weeks"
				:number="i.toString()"
				:selected="getIfSelected(i)"
			/>
		</ul>
	</nav>
</template>

<style scoped>
.icon {
	font-size: 2rem;
	cursor: pointer;
}

ul {
	display: flex;
	flex-direction: column;
	gap: 2px;
	border-radius: 1rem 1rem 0 0;
	width: 40%;
	background-color: #f9f9fb;
	padding: 1.5rem 2rem;
}

nav {
	position: sticky;
	display: flex;
	flex-direction: column;
	background-color: #f9f9fb;
	padding-bottom: 0.5rem;

	& div {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1rem 2rem;
	}

	& ul {
		padding: 0;
		width: 100%;
		max-height: 0px;
		overflow: hidden;
		transition: max-height 0.3s ease-in-out;
	}

	.shown {
		max-height: 1500px;
	}
}

h3 {
	font-size: 1.3rem;
	font-weight: 600;
}
</style>
