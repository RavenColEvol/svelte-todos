<script>
    export let todos;
    let input = '';
    const handleSubmit = (event) => {
        event.preventDefault();
        const id = todos.length ? todos[0].id + 1 : 1;
        todos.unshift({ 
            text: input,
            done: false,
            id: id
        });
        todos = todos;
        input = '';
    }
</script>

<form id='todo-form' on:submit={handleSubmit}>
    <input bind:value={input} placeholder="Enter your todo here"/>
    <button type="submit">Add Todo</button>
</form>

<style>
    #todo-form {
        display: grid;
        margin: 1rem;
        gap: 1rem;
    }

    #todo-form input{
        font-size: 1.6rem;
        padding: .75rem 1.5rem;
    }

    #todo-form button {
        font-size: 1.6rem;
        padding: .75rem 1rem;
        color: var(--secondary);
    }
</style>