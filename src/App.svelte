<script>
  import TodoCard from "./TodoCard.svelte";
  let cards = [
    {
      todo: "Belajar CSS",
      list: "task",
    },
    {
      todo: "Belajar JS",
      list: "task",
    },
    {
      todo: "Belajar ES6",
      list: "task",
    },
    {
      todo: "Belajar Svelte",
      list: "task",
    },
  ];
  let todo = "";

  function handleAddCard() {
    cards = [...cards, { todo, list: "task" }];
    console.log(`${todo} successfully added.`);
    todo = "";
  }
</script>

<div class="container my-3">
  <h3>Todo App</h3>

  <div class="card-deck">
    <div class="card bg-light">
      <div class="card-header">Todo</div>
      <div class="card-body">
        <ul class="list-group">
          {#each cards as card}
            <TodoCard content={card.todo} />
          {/each}
          <input
            type="text"
            name="todo-input"
            class="form-control mb-2"
            id="todo-input"
            bind:value={todo}
          />
          <button on:click={handleAddCard} class="btn btn-success">Add</button>
        </ul>
      </div>
    </div>
  </div>
</div>

<style>
</style>
