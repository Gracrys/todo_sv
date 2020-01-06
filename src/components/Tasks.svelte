<script>
    export let tasks 
    $: console.log(tasks)
</script>

<ul >
    {#if tasks.length < 1}
        <li>No pending tasks</li>
    {:else}
        {#each tasks as task (task.id)}
            <li class="card-action">
                <strong>{task.title}</strong>
                <p>{task.description}</p>
            </li>
        {/each}
    {/if}

</ul>

