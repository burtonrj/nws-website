<script>
    import Socials from '../socials.svelte';
</script>
  

<div class="bg-navy grid grid-cols-3 gap-4 p-4 text-white h-screen font-roboto subpixel-antialiased">
    <div class="col-span-1 flex justify-center items-center">
        <img src="/profile/profile.jpeg" alt="Profile Picture" class="w-64 h-64 rounded-full object-cover">
    </div>
    <div class="col-span-2 flex justify-center items-center">
        <div class="flex-grow">
            <h1 class="text-2xl font-bold mb-4 mx-5">Hi, I'm Harry</h1>
            <p class="mb-4 mx-5">I'm a passionate and driven third year student of ﬁlmmaking with a strong motivation and a keen eye for camera work. No Worries Productions is my 
                independant production studio through which I express my creative vision and produce professional content for clients.</p>
            <p class="mb-4 mx-5">In my work I engage in experimental film-making, create documentaries, provide production design, and camera operations, but I am also an 
                avid photographer and cinematographer. Please check out some of my work by visiting my <a href="/portfolio" class='underline'>portfolio page</a> 
                and follow me on social media using the links below.</p>
            <div class="grid grid-cols-2 gap-3 w-full">
                <div class="cols-span-1">
                    <Socials />
                </div>
                <div class="cols-span-1 flex items-center justify-center">
                    <a href="/cv/2page_HarryCV_Oct23.pdf" download class="bg-white text-black font-bold py-2 px-6 mt-4 rounded-full flex items-center justify-center">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 14.25v-2.625a3.375 3.375 0 00-3.375-3.375h-1.5A1.125 1.125 0 0113.5 7.125v-1.5a3.375 3.375 0 00-3.375-3.375H8.25m.75 12l3 3m0 0l3-3m-3 3v-6m-1.5-9H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 00-9-9z" />
                        </svg>
                        Download CV
                    </a>
                </div>
            </div>
        </div>
    </div>
</div>