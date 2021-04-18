<script>
  import { createEventDispatcher } from "svelte";

  export let content, listName, index;

  const dispatch = createEventDispatcher();
  function handleDeleteCard() {
    dispatch("deleteCard", { index });
  }
</script>

<li class="list-group-item mb-2">
  <div class="row">
    {#if listName != "To Do"}
      <div class="col-sm-1">
        <i class="fas fa-caret-left text-primary" />
      </div>
    {/if}
    <div class="col-sm-8">
      {content}
    </div>
    <div class="col-sm-1">
      <i class="fas fa-trash-alt text-danger" on:click={handleDeleteCard} />
    </div>
    {#if listName != "Done"}
      <div class="col-sm-1">
        <i class="fas fa-caret-right text-primary" />
      </div>
    {/if}
  </div>
</li>
