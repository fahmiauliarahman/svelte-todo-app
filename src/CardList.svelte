<script>
  import TodoCard from "./TodoCard.svelte";
  export let cards, listName;
  let todo = "";
  function handleAddCard() {
    cards = [...cards, { todo, list: "task" }];
    console.log(`${todo} successfully added.`);
    todo = "";
  }
</script>

<div class="card bg-light">
  <div class="card-header">{listName}</div>
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
