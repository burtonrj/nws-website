<script>
    import { onMount } from 'svelte';

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
<div class="bg-navy text-white font-incosolata flex flex-col items-center justify-center md:flex-row">
    <div class="bg-navy flex-1 flex flex-col items-center justify-center">
        <img 
        src={innerWidth <= 768 ? "/contact/small.png" : innerWidth >= 1024 ? "/contact/large.png" : "/contact/medium.png"} 
        alt="Home Graphic" 
        class="object-cover absolute top-0 left-0 w-full h-full"
        >
        <img src="/logo/logo_250_nbg.png"
        alt="Logo" 
        class="p-10 mt-10 relative w-96">
        <div class="p-2 mt-2 mx-10 relative font-incosolata subpixel-antialiased bg-clip-border text-center relative">
            <h1 class='font-bold text-xl'>Want to work together?</h1>
            <a href="https://www.instagram.com" target="_blank" class="flex items-center justify-center gap-x-2 mt-4 hover:underline">
                <p class='text-lg'>DM me on Instagram</p>
                <img src="/icons/coloured/instagram.png" alt="Instagram" class="w-8 h-8"/>
            </a>
            <p class='mt-5 text-lg'>Or email me - burtonharryb@gmail.com</p>
        </div>
    </div>
</div>