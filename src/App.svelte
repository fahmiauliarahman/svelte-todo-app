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

  function handleEventDeleteCard(e) {
    const data = e.detail;
    if (data.listName === "To Do") {
      todoCards.splice(data.index, 1);
      todoCards = todoCards;
    } else if (data.listName === "Doing") {
      doing.splice(data.index, 1);
      doing = doing;
    } else {
      doneCards.splice(data.index, 1);
      doneCards = doneCards;
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
      on:deleteCard={handleEventDeleteCard}
    />
    <CardList
      cards={doingCards}
      listName="Doing"
      on:addCard={handleEventAddCard}
      on:deleteCard={handleEventDeleteCard}
    />
    <CardList
      cards={doneCards}
      listName="Done"
      on:addCard={handleEventAddCard}
      on:deleteCard={handleEventDeleteCard}
    />
  </div>
</div>

<style>
</style>
