<script lang="ts">
    import {createEventDispatcher} from 'svelte';
    const dispatch = createEventDispatcher();
	import type { ITodo } from "./types";

    export let todo: ITodo;
</script>

<div class:completed={todo.completed}>
    <input type="checkbox" bind:checked={todo.completed} />
    {todo.title}
    <button on:click={() => dispatch('delete')}>Delete</button>
</div>

<style>
    .completed {
        text-decoration: line-through;	
    }
</style>