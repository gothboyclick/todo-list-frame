<script lang="ts">
  import { Input } from "postcss";

    export let content: String;
    export let completed: boolean;

</script>
<div 
    class=" w-full border-2 border-neutral-400 shadow-sm p-3 rounded-md space-x-2" 
>
    <input
     type="checkbox" bind:checked={completed} class="cursor-pointer accent-red-600"
    />
   <input type="text" bind:value={content} disabled="{completed}" class="disabled:opacity-50 disabled:line-through"/>

</div>