<script lang="ts">
	import type { ITodo } from "./types";

    export let todo: ITodo;
</script>

<div class:completed={todo.completed}>
    <input type="checkbox" bind:checked={todo.completed} />
    {todo.title}
</div>

<style>
    .completed {
        text-decoration: line-through;	
    }
</style>