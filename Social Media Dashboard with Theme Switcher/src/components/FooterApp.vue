<template>
	<footer class="attribution">
		Challenge by
		<a
			href="https://www.frontendmentor.io/profile/Juanescacha"
			target="_blank"
			>Frontend Mentor</a
		>
		Coded by
		<a
			href="https://github.com/Juanescacha"
			target="_blank"
			>Juan Camargo</a
		>
	</footer>
</template>

<style lang="scss" scoped>
	.attribution {
		font-size: 1rem;
		text-align: center;
		color: var(--big-text);
		margin-bottom: 3rem;

		a {
			color: var(--twitter);

			&:hover {
				text-decoration: underline;
			}

			@extend %link-focus;
		}
	}
</style>
