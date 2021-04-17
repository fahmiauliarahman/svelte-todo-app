<script>
  import TodoCard from "./TodoCard.svelte";
</script>

<div class="container my-3">
  <h3>Todo App</h3>

  <div class="card-deck">
    <div class="card bg-light">
      <div class="card-header">Todo</div>
      <div class="card-body">
        <ul class="list-group">
          <TodoCard content={"Belajar HTML"} />
          <TodoCard content={"Belajar CSS"} />
          <TodoCard content={"Belajar JS"} />
          <TodoCard content={"Belajar ES6"} />
        </ul>
      </div>
    </div>
  </div>
</div>

<style>
</style>
