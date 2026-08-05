<script>
	import { goto } from '$app/navigation';
	import Layout from 'components/Layout.svelte';
	import vendors from 'data/commercialVendors.json';
</script>

<Layout title="Commercial Vendors">
	<div class="center">
		<h1>Commercial Vendors</h1>
		<p>
			Check out these commercial vendors in the Community and Commercial Tent at this year's fair.
		</p>
		<p class="horizPanel">
			<button on:click={() => goto('/map?locate=commercial')}>Locate Commercial Tent</button>
		</p>
	</div>
	<ul class="vendorList">
		{#each vendors as vendor}
			<li>{vendor}</li>
		{/each}
	</ul>
</Layout>

<style lang="scss">
	.vendorList {
		width: 100%;
		max-width: 40ch;
		margin: 16px auto 0;
		padding: 0;
		list-style: none;

		li {
			padding: 10px 12px;
			border-radius: 8px;
			background-color: var(--light);
			margin-bottom: 8px;
		}
	}
</style>
