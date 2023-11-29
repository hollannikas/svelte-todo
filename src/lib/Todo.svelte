<script lang="ts">
	import type { ITodo } from "./types";

    export let todo: ITodo;
</script>

<div>
    <input type="checkbox" bind:checked={todo.completed} />
    {todo.title}
</div>