<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();
	import type { ITodo } from './types';

	export let todo: ITodo;
</script>

<li>
	<input type="checkbox" bind:checked={todo.completed} />
	<span class:completed={todo.completed}>{todo.title}</span>
	<button on:click={() => dispatch('delete')}>Delete</button>
</li>

<style>
	.completed {
		text-decoration: line-through;
	}
</style>
