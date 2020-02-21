<script>
  import Header from "./components/Header.svelte";
  import Char from "./components/Char.svelte";
  import AddCharForm from "./components/AddCharForm.svelte";

  let chars = [
    {
      id: 1,
      name: "svelte",
      lvl: 80
    },
    {
      id: 2,
      name: "react",
      lvl: 80
    },
    {
      id: 3,
      name: "vue",
      lvl: 80
    }
  ];

  const deleteChar = e => {
    chars = chars.filter(char => char.id !== e.detail);
  };

  const addChar = e => {
    const { name, lvl } = e.detail;
    const newChar = {
      name,
      lvl,
      id: chars.length
    };
    chars = [newChar, ...chars];
  };
</script>

<style>
  .main {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
</style>

<Header caption="Todo App" />
<main class="main">
  <AddCharForm on:addingChar={addChar} />
  {#if chars.length}
    {#each chars as data}
      <Char {...data} on:deletion={deleteChar} />
    {/each}
  {:else}
    <p>there are no characters yet</p>
  {/if}
</main>
