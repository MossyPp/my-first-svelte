<script lang="ts">
    import { Button, Dropdown, DropdownItem, Toggle } from 'flowbite-svelte';
    import { ChevronDownOutline, UserOutline } from 'flowbite-svelte-icons';
    export let objects:any;
    export let user:any = false;
  </script>
{#if user != false}
<Button> <slot/><UserOutline class="w-5 h-5 ms-2 text-white dark:text-white gap-px" /></Button>
{:else}
<Button> <slot/> <ChevronDownOutline class="w-5 h-5 ms-2 text-white dark:text-white gap-px" /></Button>
{/if}
<Dropdown >
  
  {#each objects as { text, type, onClick, value}}
    {#if type == "button"}
    <DropdownItem on:click={onClick} class="justify-end">{text}</DropdownItem>
    {:else if type == "toggle"}
    <li>
      <Toggle checked={value} class="rounded p-2 hover:bg-gray-100 dark:hover:bg-gray-600">{text}</Toggle>
    </li>
    {/if}

  {/each}
</Dropdown>