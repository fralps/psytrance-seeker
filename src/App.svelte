<script>
  import { onMount } from 'svelte';
  import axios from 'axios';
  import logo from './assets/svelte.png'
  import './components/TailwindCSS.svelte'
  import { toJson } from './helpers/youtubeHelper.js';

  let results;

  onMount(async () => {
    fetchYoutubeList();
  });

  const fetchYoutubeList = () => {
    const searchQuery = 'psytrance';
    const maxResults = 10;
    const apiKey = import.meta.env.VITE_APP_YOUTUBE_API_KEY;
    const apiBaseUrl = import.meta.env.VITE_APP_API_BASE_URL;

    axios.get(`${apiBaseUrl}`, {
      params: {
        part: 'snippet',
        maxResults: maxResults,
        q: searchQuery,
        type: 'video',
        key: apiKey
      }
    })
      .then(response => {
        console.log(response.data);
        results = toJson(response.data.items);
      });
  };
</script>

<section class="text-gray-600 body-font">
  <div class="container mx-auto flex px-5 py-24 items-center justify-center flex-col">
    <img class="lg:w-2/6 md:w-3/6 w-5/6 mb-10 object-cover object-center rounded" alt="hero" src={logo}>
    <div class="text-center lg:w-2/3 w-full">
      <h1 class="title-font sm:text-4xl text-3xl mb-4 font-medium text-gray-900">Svelte + Vite + TailwindCSS = 🌸🌸🌸</h1>
      <p class="mb-8 leading-relaxed">Meggings kinfolk echo park stumptown DIY, kale chips beard jianbing tousled. Chambray dreamcatcher trust fund, kitsch vice godard disrupt ramps hexagon mustache umami snackwave tilde chillwave ugh. Pour-over meditation PBR&amp;B pickled ennui celiac mlkshk freegan photo booth af fingerstache pitchfork.</p>
      <p>{results}</p>
    </div>
  </div>
</section>