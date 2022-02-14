<script>
  // @ts-ignore
  // Translations service
  import { t } from '@/services/i18n/i18n';

  // Components
  import Navbar from '@/components/shared/Navbar.svelte';
  import Banner from '@/components/shared/Banner.svelte';
  import Youtube from '@/components/youtube/Youtube.svelte';
  import Footer from '@/components/shared/Footer.svelte';
</script>

<section class="app">
  <Navbar />
  <Banner />
  <div class="block md:flex md:items-center md:grid md:grid-cols-2 mt-10">
    <div class="px-5">
      <div class="text-center">
        <h1 class="title">
          { $t('page_title') }
        </h1>

        <p class="mt-10 text-center text-lg">
          { $t('page_description')[0] }
        </p>

        <p class="mt-10 text-center text-lg">
          { $t('page_description')[1] }
        </p>

        <p class="mt-10 text-center text-lg">
          { $t('page_description')[2] }
        </p>
      </div>
    </div>
    <div>
      <Youtube />
    </div>
  </div>
  <Footer />
</section>

<style>
  .app {
    height: 100vh;
  }
</style>
