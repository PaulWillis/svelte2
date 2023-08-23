<script>
	import Library from './library/Library.svelte' 

	// function handleClick(id) {
	// 	console.log('clicked', id);
	// }
	function handleClick(event) {
		console.log("clicked", event.detail.id);
	}
</script>
<style>
	main {
		padding:vari(--spacingLarge);
	}
</style>

<main>
	<Library on:book-select ={handleClick} ></Library>
</main>
