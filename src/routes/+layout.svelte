<script lang="ts">
    import "../app.css";
    import Topbar from "$lib/components/Topbar.svelte";

  </script>
  
  <Topbar/>
  <slot />

  <style>
    :global(body){
      background: #2e3440;
    }
  </style>