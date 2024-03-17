<script>
    import Task from "$lib/Task.svelte";
    import "../app.css";
</script>
  
<slot />

<div class="p-4 h-screen flex justify-center items-center">
    <Task />
</div>
