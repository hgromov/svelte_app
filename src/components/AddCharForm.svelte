<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  const char = { name: "", lvl: "" };

  const forwardChar = e => {
    e.preventDefault();
    if (char.name && char.lvl) {
      dispatch("addingChar", char);
      char.name = "";
      char.lvl = "";
    }
  };
</script>

<style>
  .add-form {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-top: 10px;
    padding-top: 10px;
  }
  .inp {
    width: 220px;
    margin-bottom: 2px;
  }
  .btn {
    width: 224px;
    margin-bottom: 10px;
  }
</style>

<form class="add-form" on:submit={forwardChar}>
  <input class="inp" type="text" placeholder="name.." bind:value={char.name} />
  <input class="inp" type="number" placeholder="lvl.." bind:value={char.lvl} />
  <button class="btn" type="submit">submit</button>
</form>
