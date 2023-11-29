<script lang="ts">
	import type { ITodo } from '$lib/types';
    import Todo from '$lib/Todo.svelte';

    let todos: ITodo[] = [
        { id: 1, title: 'Do the dishes', completed: false },
        { id: 2, title: 'Take out the trash', completed: false },
        { id: 3, title: 'Mow the lawn', completed: false }
    ];

    let title = '';

    const addTodo = () => {
        todos = [...todos, { id: todos.length + 1, title, completed: false }];
        title = '';
    };

    const deleteTodo = (id: number) => {
        todos = todos.filter(todo => todo.id !== id);
    };
</script>

<h1>TODOs</h1>

<ul>
    {#each todos as todo}
        <Todo {todo} on:delete={() => deleteTodo(todo.id)}/>
    {/each}
</ul>

<input bind:value={title}/><button on:click={addTodo}>Add</button>

<style>
    ul {
        list-style: none;
        padding: 0;
    }
</style>
