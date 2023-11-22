<script>
    import { onMount } from 'svelte';
    import Desktop from './desktop.svelte';
    import Mobile from './mobile.svelte';
    let innerWidth;
  
    onMount(() => {
        innerWidth = window.innerWidth; // once the component is mounted, we're in the client and we can access the window object
        const handleResize = () => {
            innerWidth = window.innerWidth;
        };
        window.addEventListener('resize', handleResize);

        return () => {
            window.removeEventListener('resize', handleResize);
        };
    });
</script>

{#if innerWidth > 768}
    <Desktop />
{:else}
    <Mobile />
{/if}
