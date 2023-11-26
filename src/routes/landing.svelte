<script>
    import { onMount } from 'svelte';
    import Typewriter from 'svelte-typewriter';
    import Socials from './socials.svelte';

    let innerWidth = 768; // default to mobile layout during server-side rendering
    let strings = ['Short films.', 'Music videos.', '', ''];

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

<div class="bg-navy text-white font-roboto flex flex-col items-center justify-center md:flex-row">
    <div class="bg-navy flex-1 flex flex-col items-center justify-center">
        <img 
        src={innerWidth <= 768 ? "/home_graphic/small.png" : innerWidth >= 1024 ? "/home_graphic/large.png" : "/home_graphic/medium.png"} 
        alt="Home Graphic" 
        class="object-cover absolute top-0 left-0 w-full h-full"
        >
        <img src="/logo/logo_250_nbg.png"
        alt="Logo" 
        class="p-10 mt-10 relative w-96">
        {#if innerWidth > 768}
            <div class="p-2 mt-2 mx-10 relative font-roboto subpixel-antialiased bg-clip-border text-center relative">
                <h1 class='font-bold text-xl'>Photographer | Cinematographer | Film-Maker</h1>
                <p class='mt-5 text-lg'>Professional film and photography with attention to detail.</p>
            </div>
            <Socials />
        {/if}
    </div>
    <div class="flex-1">
        <div class="p-10 mt-20">
            <Typewriter
            mode={'loop'}
            wordInterval={3000}
            interval={200}
            strings={strings}>
                <h1 id='typewriter' class="relative mx-3 text-center">Short films.</h1>
                <h1 id='typewriter' class="relative mx-3 text-center">Music videos.</h1>
                <h1 id='typewriter' class="relative mx-3 text-center">Reels and shorts.</h1>
                <h1 id='typewriter' class="relative mx-3 text-center">Production design.</h1>
            </Typewriter>
        </div>
    </div>
    {#if innerWidth <= 768}
        <div class='mb-5'>
           <Socials />
        <div/>
    {/if}
</div>
