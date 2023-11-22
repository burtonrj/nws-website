<script>
    import { onMount } from 'svelte';
    import VideoCard from './video-card.svelte';
    import OtherCard from './other-card.svelte';
    import InProgressCard from './in-progress-card.svelte';

    let innerWidth = 768; // default to mobile layout during server-side rendering

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

<section class="bg-navy text-white font-roboto">
    <div class="max-w-screen-xl px-6 py-8 mx-auto lg:px-6 sm:py-16 lg:py-24">
        <h1 class='text-5xl mt-7'>Portfolio & Contributions</h1>

        <div class="grid grid-cols-1 mt-12 flex items-center justify-center text-center sm:mt-16 gap-x-20 gap-y-12 sm:grid-cols-2 lg:grid-cols-3">
            <InProgressCard
                type="Short Film"
                date="TBA"
                title="Checkmate"
                contributions="Co-writer/Director"
                producer="No Worries Productions"
            />
            <InProgressCard
                type="Documentary"
                date="TBA"
                title="CheriTang Doc"
                contributions="Co-writer/Director"
                producer="No Worries Productions"
            />
            <InProgressCard
                type="Advertisement"
                date="TBA"
                title="CheriTang Reels"
                contributions="Co-writer/Director"
                producer="No Worries Productions"
            />
            <OtherCard
                type="Live Event"
                date="Apr 2023"
                title="CheriTang Live"
                contributions="Director of Photography/Camera Operator"
                producer="No Worries Productions"
                linkType="instagram"
                link="https://www.instagram.com/reel/Ck8ShCej9ic"
            />
            <OtherCard
                type="Advertisement"
                date="Apr 2023"
                title="Family Food Action"
                contributions="Director of Photography/Camera Operator"
                producer="UWE Production"
                linkType="tik-tok"
                link="https://www.tiktok.com/@familyfoodaction"
            />
            <OtherCard
                type="Live Event"
                date="Feb 2022-2023"
                title="Sports Live Stream"
                contributions="Camera Operator"
                producer="UWE Production" 
                linkType="youtube" 
                link="https://www.youtube.com/watch?v=oh5XSq3EyZg"
            />
            <VideoCard
                type="Short Film"
                date="Apr 2023"
                title="Inception of Silence"
                contributions="Production Design Assistant"
                producer="JustJust Productions"
                youtubeLink="https://www.youtube.com/embed/vH9macba4C8?si=A0KHJFmlFaB5rukR"
                innerWidth={innerWidth}
            />
            <VideoCard
                type="Documentary"
                date="Nov 2022"
                title="Arrow In Flight"
                contributions="Director of Photography/Camera Operator"
                producer="UWE Production"
                youtubeLink="https://www.youtube.com/embed/8dHRhizSM6c?si=aKTD5BTsKyC-zp5O"
                innerWidth={innerWidth}
            />
            <VideoCard
                type="Short Film"
                date="Apr 2022"
                title="Be careful what you wish for"
                contributions="Director of Photography/Camera Operator"
                producer="UWE Production"
                youtubeLink="https://www.youtube.com/embed/MwXwTh4cEJE?si=cNxCM3qBAaL4Hmg5"
                innerWidth={innerWidth}
            />
            <VideoCard
                type="Short Film"
                date="Apr 2022"
                title="Devil You Know"
                contributions="Director/DOP/Camera Operator"
                producer="No Worries Production"
                youtubeLink="https://www.youtube.com/embed/MwXwTh4cEJE?si=cNxCM3qBAaL4Hmg5"
                innerWidth={innerWidth}
            />
            <VideoCard
                type="Short Film"
                date="Dec 2021"
                title="High ﬁdelity"
                contributions="Gaffer"
                producer="UWE Production"
                youtubeLink="https://www.youtube.com/embed/OJOP8aGk3mo?si=kzd3Zx5HVg6Qm5pH"
                innerWidth={innerWidth}
            />
            <VideoCard
                type="Music Video"
                date="Mar 2021"
                title="Falling Asleep At The Wheel"
                contributions="Director of Photography/Camera Operator"
                producer="Colchester Institute Production"
                youtubeLink="https://www.youtube.com/embed/2Spgdw8JRmI?si=naynvS3_cHSUdifZ"
                innerWidth={innerWidth}
            />
        </div>
    <div>
</section>