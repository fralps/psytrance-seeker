<script>
  export let video;
</script>

<section class="w-full text-white uppercase border-b-4 transition ease-in-out delay-100 bg-black hover:-translate-y-1 hover:scale-102 hover:bg-white duration-200 hover:text-black hover:border-b-4 rounded">
  <div class="px-6 py-4">
    <div class="font-bold text-xl">{video.snippet.title.substring(65, 1)}</div>
  </div>
</section>
