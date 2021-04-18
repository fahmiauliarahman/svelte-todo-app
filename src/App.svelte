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

  function handleEventAddCard(e) {
    const data = e.detail;
    if (data.listName === "To Do") {
      todoCards = [...todoCards, { todo: data.todo }];
    } else if (data.listName === "Doing") {
      doingCards = [...doingCards, { todo: data.todo }];
    } else {
      doneCards = [...doneCards, { todo: data.todo }];
    }
  }
</script>

<div class="container my-3">
  <h3>Todo App</h3>

  <div class="card-deck">
    <CardList
      cards={todoCards}
      listName="To Do"
      on:addCard={handleEventAddCard}
    />
    <CardList
      cards={doingCards}
      listName="Doing"
      on:addCard={handleEventAddCard}
    />
    <CardList
      cards={doneCards}
      listName="Done"
      on:addCard={handleEventAddCard}
    />
  </div>
</div>

<style>
</style>
