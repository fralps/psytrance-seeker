<script>
  import { locale, locales } from '../../services/i18n/i18n';
</script>

<section>
  <select class="border m-4 cursor-pointer" bind:value={$locale}>
    { #each locales as locale }
      <option value={locale}>{ locale }</option>
    { /each }
  </select>
</section>
