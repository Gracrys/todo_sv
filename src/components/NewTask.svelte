<script>
import { createEventDispatcher } from 'svelte';
let task = {}
let dispatch = createEventDispatcher();

	function send() {
        if(task.title.length > 5)
            dispatch('newTask', task);
        else
            alert("No content")
        task = {title: "", description: "" }
	}
</script>

<form action="" class="card-content p-4">
  <input type="text" class="title" bind:value={task.title} placeholder="Title" required>
  <textarea id="" name="" class="materialize-textarea" bind:value={task.description} required placeholder="Description"></textarea>
  <button on:click|preventDefault={send}>New Task</button>
</form>
