<script setup>
	import OverviewCard from "./OverviewCard.vue"
	import DashboardCard from "./DashboardCard.vue"
	const props = defineProps({
		followers: Array,
		title: String,
		todayOverview: Array,
	})
</script>

<template>
	<main class="main">
		<section class="main__first-container">
			<h2 class="sr-only">Dashboard</h2>
			<DashboardCard
				v-for="card in props.followers"
				:key="card.name"
				:card="card" />
		</section>
		<section class="main__second-container">
			<h2 class="main__subtitle">{{ props.title }}</h2>
			<OverviewCard
				v-for="card in props.todayOverview"
				key="card.type"
				:card="card" />
		</section>
	</main>
</template>

<style lang="scss" scoped>
	.main {
		padding: 0 1.56rem 2.81rem 1.56rem;
		margin-top: -2.75rem;

		&__first-container {
			display: flex;
			flex-direction: column;
			gap: 1.5rem;
		}

		&__second-container {
			display: flex;
			flex-direction: column;
			gap: 1rem;
		}

		&__subtitle {
			color: var(--big-text);
			font-size: 1.5rem;
			font-weight: 700;
			text-transform: capitalize;
			margin-top: 2.88rem;
			margin-bottom: calc(1.69rem - 1rem);
		}
	}

	@media (min-width: $small-breakpoint) {
		.main {
			padding-bottom: 4.69rem;
			padding-left: 10.31rem;
			padding-right: 10.31rem;
			margin-top: -6.75rem;

			&__first-container {
				flex-direction: row;
				flex-wrap: wrap;
				gap: 1.88rem;
			}

			&__second-container {
				display: grid;
				grid-template-columns: repeat(4, minmax(0, 1fr));
				gap: 0;
				row-gap: 1.5rem;
				column-gap: 1.88rem;
			}
			&__subtitle {
				grid-column: 1 / -1;
				margin-bottom: 0;
			}
		}
	}
</style>
