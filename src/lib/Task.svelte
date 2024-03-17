<script lang="ts">
    export let content: string; 
    export let completed: boolean;
</script>

<div class="bg-purple-500 w-full bg-brown border border-neutral-300 shadow-sm p-3 rounded-md space-x-2">
    <input 
        type="checkbox" 
        bind:checked={completed} 
        class="cursor-pointer accent-yellow-500" 
    />
    <input 
        type="text" 
        bind:value={content} 
        disabled={completed}
        class="disabled:opacity-50 disabled:line-through rounded-md p-2" 
    />
</div>
