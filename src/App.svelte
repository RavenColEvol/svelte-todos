<script>
	import TodoInput from "./components/TodoInput.svelte";
	import TodoItem from './components/TodoItem.svelte';
	let todos = [
		{ id: 1, text: 'Learn Svelte', done: false },
		{ id: 2, text: 'Learn Svelte', done: true },
	];
</script>

<main>
	<TodoInput bind:todos />
	{#each todos as todo}
		<TodoItem todo={todo} bind:todos/>
	{/each}
</main>

<style>
	
</style>