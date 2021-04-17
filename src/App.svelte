<script>
  import CardList from "./CardList.svelte";
  let todoCards = [
    {
      todo: "Belajar CSS",
      list: "task",
    },
  ];

  let doingCards = [];
  let doneCards = [];
</script>

<div class="container my-3">
  <h3>Todo App</h3>

  <div class="card-deck">
    <CardList cards={todoCards} listName="To Do" />
    <CardList cards={doingCards} listName="Doing" />
    <CardList cards={doneCards} listName="Done" />
  </div>
</div>

<style>
</style>
