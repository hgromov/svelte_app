<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  export let name;
  export let lvl;
  export let id;
  let isExpand = false;

  const toggle = () => {
    isExpand = !isExpand;
  };

  const dispatchDelete = () => {
    dispatch("deletion", id);
  };
</script>

<style>
  .char {
    width: 200px;
    position: relative;
    margin: 10px 0;
    padding: 10px;
    background: #ffffed;
    border: 1px solid #333;
    border-radius: 3px;
    display: flex;
    flex-direction: column;
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
      "Lucida Sans", Arial, sans-serif;
  }
  .name {
    align-self: center;
    font-size: 18px;
    color: red;
  }
  .lvl {
    display: inline-block;
    max-width: 100px;
    font-size: 12px;
    color: blue;
    align-self: left;
  }
  .controls {
    position: absolute;
    right: 10px;
    align-self: center;
  }
  .btn {
    width: 20px;
    height: 20px;
    padding: 0 0 5px;
    text-align: center;
    line-height: 16px;
  }
  .ico {
    width: 100%;
    height: 100%;
  }
  .controll-form {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-top: 10px;
    padding-top: 10px;
    border-top: 1px solid #c0c0c0;
  }
  .inp {
    width: 45%;
  }
</style>

<div class="char">
  <span class="name">{name}</span>
  <div class="controls">
    <button class="btn" on:click={toggle}>
      {#if isExpand}-{:else}+{/if}
    </button>
    <button class="btn" on:click={dispatchDelete}>
      <img class="ico" src="assets\times-solid.svg" alt="x" />
    </button>
  </div>
  <span class="lvl">lvl: {lvl}</span>
  {#if isExpand}
    <div class="controll-form">
      <input class="inp" type="text" bind:value={name} />
      <input class="inp" type="number" bind:value={lvl} />
    </div>
  {/if}
</div>
