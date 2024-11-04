<script lang="ts">
	let input = $state('');
	let html = $state('');

	const handleSearch = async () => {
		const res = await fetch('https://jsonplaceholder.typicode.com/todos/1').then((response) =>
			response.json()
		);
		html = JSON.stringify(res);
	};
</script>

<div class="input">
	<input type="text" bind:value={input} />
	<button onclick={handleSearch}>search</button>
</div>
{html}

<style>
	.input {
		margin-bottom: 20px;
	}
</style>
