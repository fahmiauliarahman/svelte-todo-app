<script>
  import TodoCard from "./TodoCard.svelte";
  // let contents = ["Belajar CSS", "Belajar JS", "Belajar ES6", "Belajar Svelte"]; //array of strings
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
</script>

<div class="container my-3">
  <h3>Todo App</h3>

  <div class="card-deck">
    <div class="card bg-light">
      <div class="card-header">Todo</div>
      <div class="card-body">
        <ul class="list-group">
          <!-- For array of strings -->
          <!-- {#each contents as content} -->
          <!-- <TodoCard content={content} /> -->
          <!-- <TodoCard {content} /> -->
          <!-- {/each} -->

          <!-- for array of objects -->
          {#each cards as card}
            <TodoCard content={card.todo} />
          {/each}
        </ul>
      </div>
    </div>
  </div>
</div>

<style>
</style>
