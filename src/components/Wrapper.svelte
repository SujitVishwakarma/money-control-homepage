<script>
  import { Router, Route } from 'svelte-routing';
  import ChatBox from './ChatBox.svelte';
  import NewsList from './newsContents/NewsList.svelte';
  import MagazinePage from './newsContents/Magazine.svelte';

  let currentCategory = 'general';

  function setCategory(category) {
    currentCategory = category;
  }
</script>

<style>
  .container {
    display: flex;
    height: 100vh;
    overflow: hidden;
    width: 100vw;
  }
  .main-content {
    flex: 1;
    overflow-y: auto;
    padding: 1rem;
  }
  .main-content::-webkit-scrollbar {
    display: none;
  }
  .main-content {
    -ms-overflow-style: none;  /* IE and Edge */
    scrollbar-width: none;  /* Firefox */
  }
</style>

<div class="container mx-auto mt-8 px-4 sm:px-6 lg:px-8 overflow-y-hidden flex-col sm:flex-row items-center sm:items-center">
  <div class="main-content">
    
    <slot></slot>
  </div>
</div>
