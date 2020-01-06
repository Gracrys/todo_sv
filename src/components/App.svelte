<script>
  export let name;
  import Tasks from './Tasks.svelte';
  import NewTask from './NewTask.svelte';
  let ids = 0;
  let tasks = []
  let newTask = (x) => {x.detail.id = ++ids; tasks = [...tasks,x.detail]; }
  let erase = (x) => tasks = tasks.filter(y => y.id != x.detail)

</script>

<style>
  h4 {
    text-align: center;
    font-weight: bolder;
    animation: 5s wave infinite; 
    color: cyan;
  }
    @keyframes wave{
        from {
            filter: hue-rotate(0deg)
        }
        to {
            filter: hue-rotate(360deg)
        }
    }
</style>

<main>
  <h4>Welcome again</h4>
  <NewTask on:newTask={newTask}/>
  <Tasks bind:tasks={tasks} on:delete={erase} />
</main>
