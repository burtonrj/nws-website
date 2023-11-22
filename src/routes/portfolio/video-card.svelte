<script>
    import Youtube from "./youtube.svelte";
    export let youtubeLink;

    export let innerWidth;
    
    export let type;
    export let date;
    export let title;
    export let contributions;
    export let producer;
</script>
<div class="space-y-2 flex flex-col items-center">
    <span
      class="bg-gray-100 text-gray-900 text-xs font-medium inline-flex items-center px-2.5 py-0.5 rounded dark:bg-gray-700 dark:text-gray-300">
      {type}
    </span>
    <h3 class="text-2xl font-roboto leading-tight text-gray-900 dark:text-white">
        {title}
    </h3>
    <p class="text-lg font-roboto text-gray-500 dark:text-gray-400">
        <span class="font-bold">Contributions:</span> {contributions}<br>
        <span class="font-bold">Production by:</span> {producer}
    </p>
    <p class="flex items-center gap-x-2">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5m-9-6h.008v.008H12v-.008zM12 15h.008v.008H12V15zm0 2.25h.008v.008H12v-.008zM9.75 15h.008v.008H9.75V15zm0 2.25h.008v.008H9.75v-.008zM7.5 15h.008v.008H7.5V15zm0 2.25h.008v.008H7.5v-.008zm6.75-4.5h.008v.008h-.008v-.008zm0 2.25h.008v.008h-.008V15zm0 2.25h.008v.008h-.008v-.008zm2.25-4.5h.008v.008H16.5v-.008zm0 2.25h.008v.008H16.5V15z" />
        </svg>
        {date}
    </p>
    <div class="inline-flex items-center">
      {#if innerWidth <= 768}
        <Youtube link={youtubeLink} width="280" height="157" />
      {:else if 768 < innerWidth < 1080}
        <Youtube link={youtubeLink} width="370" height="208" />
      {:else}
        <Youtube link={youtubeLink} width="560" height="315" />
      {/if}
    </div>
</div>