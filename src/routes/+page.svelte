<script lang="ts">
    import Task from "$lib/Task.svelte";
    import "../app.css";

    interface ITask {
        text: string;
        completed: boolean; 
    }

    let tasks: ITask[] = [
        {
            text: "Minha tarefa!",
            completed: false
        }
    ];

    const addTask = () => {
        tasks = [
            ...tasks, 
            {
                text: "Nova task",
                completed: false,
            },
        ]
    }
</script>

<slot />

<div class="p-4 h-screen flex justify-center items-center flex-col space-y-2 max-w-lg mx-auto">

    {#each tasks as task}
        <Task bind:content={task.text} bind:completed={task.completed} />
    {/each}

    <button 
        class="w-full flex justify-center items-center space-x-2 text-neutral-700 border-2 border-neutral-300 p-3 rounded-lg border-dashed font-semibold"
        on:click={addTask}
    >
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M12 9v6m3-3H9m12 0a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
        </svg>
        <span>Add Task</span>
    </button>
</div>
