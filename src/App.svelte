<script>
  import Header from "./components/Header.svelte";
  import Char from "./components/Char.svelte";

  const chars = [
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
</script>

<style>
  .main {
    display: flex;
    justify-content: center;
  }
</style>

<Header />
<main class="main">
	<Char name='vasya' lvl='7' />
</main>
