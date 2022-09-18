<script>
// @ts-ignore
import { onMount } from "svelte";
  let todos = [];
  let todoText = '';

  onMount(() => {
    const existingTodos = localStorage.getItem('todos');
  });

  function newTodo() {
    todos = [...todos, todoText];
    localStorage.setItem('todos', JSON.stringify(todos));
  }


</script>

<main>
  <ul>
    {#each todos as todo}
    <li>{todo}</li>
    {/each}
  </ul>
  <form on:submit|preventDefault={newTodo}>
  <input bind:value={todoText}>
  <input type="submit" value="New Todo...">
  </form>
</main>

<style>

</style>