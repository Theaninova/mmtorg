<script lang="ts">
  import {fly} from "svelte/transition"

  export let activeRoute: string
</script>

{#key activeRoute}
  <main in:fly={{duration: 250, delay: 300, x: -150}} out:fly={{duration: 250, x: -150}}>
    <slot />
  </main>
{/key}

<style global>
  main {
    grid-row: 2;
    grid-column: 1;
    will-change: transform, opacity;
  }
</style>
