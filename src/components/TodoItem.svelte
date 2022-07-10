<script>
    export let todo;
    export let todos;
    const handleDelete = ({id}) => {
        todos = todos.filter(todo => {
            return todo.id !== id;
        });
    }

    const handleCheck = ({id}) => {
        todos = todos.map(todo => {
            if (todo.id === id) {
                todo.done = !todo.done;
            }
            return todo;
        });
    }
</script>

<div class='todo-item'>
    <span class={todo.done && 'todo-item__done'}>
        {todo.text}
    </span>
    <div>
        <span class='btn' on:click={() => handleDelete(todo)}>
            🗑️
        </span>
        <span class='btn' on:click={() => handleCheck(todo)}>
            ✅
        </span>
    </div>
</div>

<style>
    .todo-item {
        font-size: 1.6rem;
        padding: .75rem 1rem;
        display: flex;
        width: 100%;
        justify-content: space-between;
    }

    .todo-item__done {
        text-decoration: line-through;
    }
    
    .todo-item:nth-child(odd) {
        background-color: #eee;
    }

    .btn {
        display: inline-block;
        cursor: pointer;
        margin-right: .5rem;
    }
</style>