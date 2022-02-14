<script>
  // @ts-ignore
   import { t } from '@/services/i18n/i18n';
</script>

<section class="h-20 border-t-4 border-b-4 banner">
  <p class="banner-text">{ $t('page_banner') }</p>
</section>

<style>
  .banner {
   overflow: hidden;
  }

  .banner .banner-text {
    font-size: 3rem;
    color: white;
    margin: 0;
    /* Starting position */
    -moz-transform:translateX(100%);
    -webkit-transform:translateX(100%);	
    transform:translateX(100%);
    /* Apply animation to this element */	
    -moz-animation: banner 12s linear infinite;
    -webkit-animation: banner 12s linear infinite;
    animation: banner 12s linear infinite;
  }

  /* Move it (define the animation) */
  @-moz-keyframes banner {
    0%   { -moz-transform: translateX(100%); }
    100% { -moz-transform: translateX(-100%); }
  }

  @-webkit-keyframes banner {
    0%   { -webkit-transform: translateX(100%); }
    100% { -webkit-transform: translateX(-100%); }
  }

  @keyframes banner {
    0%   { 
    -moz-transform: translateX(100%); /* Firefox bug fix */
    -webkit-transform: translateX(100%); /* Firefox bug fix */
    transform: translateX(100%); 		
   }
  
   100% { 
    -moz-transform: translateX(-100%); /* Firefox bug fix */
    -webkit-transform: translateX(-100%); /* Firefox bug fix */
    transform: translateX(-100%); 
   }
  }
  </style>