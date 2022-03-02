<script>
  import { onMount } from 'svelte';
  import { searchList } from '@/constants/searchList.js';
  import { t } from '@/services/i18n/i18n';
  import axios from 'axios';
  import Card from '@/components/youtube/Card.svelte';

  const youtubeVideoUrl = 'https://www.youtube.com/watch?v=';

  let videos = [];
  let isFetchingVideos = false;
  let isErrorPresent = false;
  let searchTerm = searchList[Math.floor(Math.random() * searchList.length)];
  
  onMount(async () => {
    isFetchingVideos = true;
    const searchQuery = searchTerm;
    const maxResults = 5;
    const apiKey = import.meta.env.VITE_APP_YOUTUBE_API_KEY;
    const apiBaseUrl = import.meta.env.VITE_APP_API_BASE_URL;

    await axios.get(`${apiBaseUrl}`, {
      params: {
        part: 'snippet',
        maxResults: maxResults,
        q: searchQuery,
        type: 'video',
        key: apiKey
      }
    })
      .then(response => {
        videos = response.data.items;
        isFetchingVideos = false;
      })
      .catch(() => {
        isFetchingVideos = false;
        isErrorPresent = true;
      });
	});
</script>

<section class="mt-4 test">
  <div class="flex flex-col items-center mr-4">
    {#if isFetchingVideos}
      <div class="rotating text-6xl">
        💊
      </div>
    {:else}
      {#if isErrorPresent}
        <div class="text-sm text-center">{$t('api_error')}</div>
      {:else}
        {#each videos as video }
          <a href={`${youtubeVideoUrl}${video.id.videoId}`} target="_blank" class="w-full">
            <Card video={video} />
          </a>
        {/each}
      {/if}
    {/if}
  </div>
</section>

<style lang="scss">
  @import '../../assets/styles/variables';

  @keyframes rotating {
    from {
      -webkit-transform: rotate(0deg);
    }

    to {
      -webkit-transform: rotate(360deg);
    }
  }

  .rotating {
    animation: rotating 2s linear infinite;
  }
</style>
