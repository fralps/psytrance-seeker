<script>
  import { locale, locales } from '@/services/i18n/i18n';

  // Change flag depending on locale
  const handleFlag = (locale) => {
    switch (locale) {
      case 'fr':
        return `🇫🇷 ${locale}`;
      case 'en':
        return `🇬🇧 ${locale}`;
    }
  };
</script>

<section class="text-right">
  <select class="border bg-black cursor-pointer py-2 px-2 rounded my-4 mx-4" bind:value={$locale}>
    { #each locales as locale }
      <option value={locale}>{ handleFlag(locale) }</option>
    { /each }
  </select>
</section>
