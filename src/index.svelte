<script>
    let newToDo = ""
    let place = 0
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

    function removeToDo(index) {
        // remove the todo at index form the todos array
        todos = [...todos.slice(0, index), ...todos.slice(index + 1)]
    }
</script>

<h1 class="title">To-Do List</h1>

<div id="addToDo">
    <label>
        To-Do: 
        <input type="text" bind:value={newToDo}>
    </label>

    <button on:click={addToDo}>Add To-Do</button>
</div>

<div id="removeToDo">
    <label>
        Remove: 
        <input type="number" bind:value={place}>
    </label>

    <button on:click={ () => { removeToDo(place) } }>Remove: </button>
</div>

<ul class="list">
    {#each todos as todo, index}
    <li class="list-item">{index}: {todo}</li>
    {/each}
</ul>