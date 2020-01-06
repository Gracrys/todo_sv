<script>
    export let tasks 
    import { createEventDispatcher } from 'svelte';
    let dispatch = createEventDispatcher();
    const erase = (x) => {
        dispatch('delete', x)    
    }
</script>

<ul >
    {#if tasks.length < 1}
        <li>No pending tasks</li>
    {:else}
        {#each tasks as task (task.id)}
            <li class="card-action" id={task.id}>
                <button class="btn-floating pulse right" on:click={erase(task.id)}><i class="material-icons">delete</i></button>
                <strong>{task.title}</strong>
                <p>{task.description}</p>
            </li>
        {/each}
    {/if}

</ul>

