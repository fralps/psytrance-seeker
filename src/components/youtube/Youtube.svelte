<script>
  import axios from 'axios';
  import Card from './Card.svelte';

  let videos = [];

 const fetchYoutubeList = async () => {
    const searchQuery = 'psytrance';
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
      });
  };
</script>

<section class="container">
  <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-2"
    on:click|once={fetchYoutubeList}
  >
    Bring me joy
  </button>

  <div class="text-center grid grid-cols-3 gap-4">
    {#each videos as video }
      <Card video={video} />
    {/each}
  </div>
</section>
