
<script>
    import { faHeadphones } from '@fortawesome/free-solid-svg-icons';
    import { FontAwesomeIcon } from '@fortawesome/svelte-fontawesome';
  </script>
  
  <style>
    .fixed-bottom-right {
      @apply fixed bottom-4 right-4;
    }
  
    @media (max-width: 1024px) {
      .fixed-bottom-right {
        @apply bottom-20; 
      }
    }
  </style>
  
  <div class="fixed-bottom-right bg-white shadow-lg p-2 sm:p-4 rounded-full">
    <FontAwesomeIcon icon={faHeadphones}  class="w-8 h-8 sm:w-12 sm:h-12 text-red-500" />
  </div>
  