<script>
	import Header from '../components/layout/Header.svelte';
	import Footer from '../components/layout/Footer.svelte';
	import Transitions from '../components/utilities/Transitions.svelte';
	export let segment;
</script>

<style lang="scss" global>
	@import "../styles/global";
	.page-wrapper {
		padding-top: 6rem;
	}
	.hidden-crawler-links {
		display: none;
	}
</style>


<Header />
<main class="page-wrapper">
	<Transitions refresh={segment}>
		<slot></slot>
	</Transitions>
</main>
<Footer />


<div class="hidden-crawler-links">
	<a href="/ghost">Ghost</a>
	<a href="/membership">Membership</a>
</div>