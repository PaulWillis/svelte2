<script>
	import Detail from "./detail/Detail.svelte";
	import Library from "./library/Library.svelte";

	// function handleClick(id) {
	// 	console.log('clicked', id);
	// }

	let page = 'detail';
	let pageArgs = {id : 14};
	
	function handleClick(event) {
//		console.log("clicked", event.detail.id);
		page = 'detail';
		pageArgs = event.detail
	}
</script>
<style>
	main {
		padding:vari(--spacingLarge);
	}
</style>

<main>
	{#if page=== 'detail' }
		<Detail {...pageArgs} />
	{:else}
		<Library on:book-select ={handleClick} ></Library>
	{/if}
</main>
