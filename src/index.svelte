<script>
    let newToDo = ""
    let todos = [
        "Write essay",
        "Code to-do list",
        "Work on stats",
        "Complete physics questions"
    ]

    function addToDo() {
        // add the newToDo to the end of the todos array
        todos = [...todos, newToDo]
    }
</script>

<h1 class="title">To-Do List</h1>

<label>
    To-Do: 
    <input type="text" bind:value={newToDo}>
</label>

<button on:click={addToDo}>Add To-Do</button>

<ul class="list">
    {#each todos as todo}
    <li class="list-item">{todo}</li>
    {/each}

</ul>