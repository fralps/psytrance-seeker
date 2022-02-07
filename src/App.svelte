<script>
  // Translations service
  import { t } from './services/i18n/i18n';

  // Main styles
  import './components/shared/TailwindCSS.svelte';
  import './assets/styles/app.css';

  // Components
  import Navbar from './components/shared/Navbar.svelte';
  import Youtube from './components/youtube/Youtube.svelte';
</script>

<section class="text-gray-600 body-font">
  <Navbar />
  <div class="container mx-auto flex px-5 py-24 items-center justify-center flex-col">
    <div class="text-center w-full">
      <h1 class="title-font sm:text-4xl text-3xl mb-4 font-medium text-gray-900">
        { $t('page_title') }
      </h1>
      <Youtube />      
    </div>
  </div>
</section>
