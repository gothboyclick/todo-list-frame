<script lang="ts">
    import Task from "$lib/Task.svelte";

    interface ITask{
        text: String;
        completed: boolean;
    }
    
    let tasks: ITask[] = [
        {
            text:"essa task é genérica",
            completed: false,
        },
        {
            text:"essa ainda é genérica",
            completed: true,
        }
    ];
function addTask(){
    tasks = [...tasks,{
        text:"task 3",
        completed: false,
    },
    ];
}


</script>
<div class="p-4 h-screen flex justify-center items-center flex-col space-y-2 max-w-lg mx-auto bg-red-500">
    {#each tasks as task}
        <Task bind:content="{task.text}" bind:completed="{task.completed}"/>
    {/each}
    <button 
        class="w-full flex justify-center border-3 text-neutral-500 border-neutral-300 p-3 rounded-lg border-dashed font-semibold"
        on:click="{addTask}"
    >
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M12 9v6m3-3H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z" />
        </svg>
    <span> Adicionar Tarefa</span>
    </button>
</div>
<style lang="postcss"></style>