<script>
    export let tasks = []
</script>

<ul>
    {#if tasks.length < 1}
        <li>No pending tasks</li>
    {:else}
        {#each tasks as task (task.id)}
            <li>{task}</li>
        {/each}
    {/if}

</ul>

