<script>
  export let video;
  export let searchTerm;
</script>

<section class="mt-4">
  <div class="card max-w-sm rounded overflow-hidden shadow-lg">
    <img class="w-full" src={video.snippet.thumbnails.medium.url} alt="youtube-img">
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">{video.snippet.title}</div>
      <p class="text-gray-700 text-base">
        {video.snippet.description}
      </p>
    </div>
    <div class="px-6 pt-4 pb-2">
      <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#{video.snippet.channelTitle}</span>
      <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#{searchTerm}</span>
    </div>
  </div>
</section>

<style>
  .card {
    min-height: 600px;
    max-height: 500px;
  }
</style>
