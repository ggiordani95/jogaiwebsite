<script lang="ts">

import { onMount } from 'svelte';
  import HeaderSection from '$lib/HeaderSection.svelte';
  import ResourcesSection from '$lib/ResourcesSection.svelte';
  import PlansSection from '$lib/PlansSection.svelte';
  import MockupSection from '$lib/MockupSection.svelte';


  let loaded = false;

  onMount(() => loaded = true);
</script>

<div class="bg-primary-bg flex flex-col justify-center items-center select-none p-0">
    {#if loaded}
        <HeaderSection/>
        <ResourcesSection/>
        <PlansSection/>
        <MockupSection/>
    {/if}
</div>

<style lang="postcss">
    :global(html) {
      background-color: theme(colors.gray.100);
    }
</style>