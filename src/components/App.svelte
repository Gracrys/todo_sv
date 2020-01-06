<script>
  export let name;
  import Tasks from './Tasks.svelte';
</script>

<style>
  h1 {
    text-align: center;
  }
</style>

<main>
  <h1>Hello {name}!</h1>
  <NewTask />
  <Tasks />
</main>
