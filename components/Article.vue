<template>
	<div class="article">
		<Header img="https://picsum.photos/800/600" />
		<article>
			<slot />
		</article>
	</div>
</template>

<style>
.article {
	display: flex;
	align-items: stretch;
	min-height: 100vh;

	margin: 1rem 1rem 0;
	gap: 1rem;

	& article {
		width: 60%;
		margin-bottom: 3rem;

		display: flex;
		flex-direction: column;
		gap: 0.5rem;

		& h1 {
			margin: 0.5rem 0;
			font-size: 2rem;
			font-weight: 600;
		}

		& a {
			margin-top: 1rem;
			font-size: 0.9rem;
			font-weight: 300;
			color: blue;
		}

		& img {
			border-radius: 1rem;
			aspect-ratio: 150 / 100;
			object-fit: cover;
			width: 100%;
			margin-bottom: 1rem;
		}
	}
}

@media screen and (max-width: 768px) {
	.article {
		flex-direction: column;
		margin: 0;

		& article {
			width: 100%;
			padding: 1rem 1rem 0;
		}
	}
}
</style>
