<script>
  import { onMount } from 'svelte';
  import axios from 'axios';
  // import { toJson } from './helpers/youtubeHelper.js';

  // Main styles
  // import logo from './assets/svelte.png';
  import './components/shared/TailwindCSS.svelte';

  // Components
  import Navbar from './components/shared/Navbar.svelte';
  import Quote from './components/Quote.svelte';

  // let results;

  onMount(async () => {
    // fetchYoutubeList();
  });

  // const fetchYoutubeList = () => {
  //   const searchQuery = 'psytrance';
  //   const maxResults = 10;
  //   const apiKey = import.meta.env.VITE_APP_YOUTUBE_API_KEY;
  //   const apiBaseUrl = import.meta.env.VITE_APP_API_BASE_URL;

  //   axios.get(`${apiBaseUrl}`, {
  //     params: {
  //       part: 'snippet',
  //       maxResults: maxResults,
  //       q: searchQuery,
  //       type: 'video',
  //       key: apiKey
  //     }
  //   })
  //     .then(response => {
  //       console.log(response.data);
  //       results = toJson(response.data.items);
  //     });
  // };
</script>

<section class="text-gray-600 body-font">
  <Navbar />
  <div class="container mx-auto flex px-5 py-24 items-center justify-center flex-col">
    <!-- <img class="lg:w-2/6 md:w-3/6 w-5/6 mb-10 object-cover object-center rounded" alt="hero" src={logo}> -->
    <div class="text-center lg:w-2/3 w-full">
      <Quote />      
    </div>
  </div>
</section>
