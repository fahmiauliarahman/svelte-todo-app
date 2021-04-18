<script>
  import { createEventDispatcher } from "svelte";

  import TodoCard from "./TodoCard.svelte";
  export let cards, listName;

  let todo = "";
  const dispatch = createEventDispatcher();

  function handleAddCard() {
    // cards = [...cards, { todo, list: "task" }];
    dispatch("addCard", { todo, listName });
    console.log(`${todo} successfully added.`);
    todo = "";
  }

  function handleDeleteCard(e) {
    const data = e.detail;
    dispatch("deleteCard", { index: data.index, listName });
  }
</script>

<div class="card bg-light">
  <div class="card-header">{listName}</div>
  <div class="card-body">
    <ul class="list-group">
      {#each cards as card, index}
        <TodoCard
          content={card.todo}
          {listName}
          {index}
          on:deleteCard={handleDeleteCard}
        />
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
