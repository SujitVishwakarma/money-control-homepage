<script>
  import {
    faNewspaper,
    faTv,
    faCrown,
    faGlobe,
    faSearch,
    faPhone,
    faBars,
  } from "@fortawesome/free-solid-svg-icons";
  import { FontAwesomeIcon } from "@fortawesome/svelte-fontawesome";
  import TopHeader from "./TopHeader.svelte";
  import ThirdNav from "./ThirdNav.svelte";
  function handleClick() {
    alert("Hello");
    console.log("clicked");
  }
 import creditClock from "../../public/creditClock.jpg";
</script>

<!-- inserted this navbar from daisyui  -->
<div
  class="flex items-center justify-between top-0 w-full text-white p-0 h-12"
  style="height: 29px;"
>
  <TopHeader />
</div>
<!-- second nav start from here  -->

<div class="flex items-center justify-between w-full p-0 h-12 bg-slate-200 shadow-md">
  <div class="flex items-center  space-x-2 ml-2">
    <img src="/politics.jpg" alt="Logo" class="w-6 h-6 rounded-full items-center" />
    <span class="font-bold text-xs">Sachtak.com</span>
  </div>
  <div class="flex space-x-2 items-center pr-2">
    <button
      on:click={handleClick}
      class="bg-red-600 text-white p-1 rounded-md flex items-center text-xs"
    >
      <FontAwesomeIcon icon={faCrown} class="w-3 h-3 mr-1" />
      Subscribe
    </button>
    <div class="hidden md:flex items-center space-x-2">
      <div class="h-6 border-l border-gray-500"></div>
      <a href="/magazine" class="flex flex-col items-center hover:text-red-600 text-xs">
        <FontAwesomeIcon icon={faNewspaper} class="w-3 h-3 mb-1" />
        <span>Magazine</span>
      </a>
      <div class="h-6 border-l border-gray-500"></div>
      <a href="#" class="flex flex-col items-center hover:text-red-600 text-xs">
        <FontAwesomeIcon icon={faTv} class="w-3 h-3 mb-1" />
        <span>Live TV</span>
      </a>
      <div class="h-6 border-l border-gray-500"></div>
      <a href="#" class="flex flex-col items-center hover:text-red-600 text-xs">
        <FontAwesomeIcon icon={faGlobe} class="w-3 h-3 mb-1" />
        <span>Language</span>
      </a>
      <div class="h-6 border-l border-gray-500"></div>
      <a href="#" class="flex flex-col items-center hover:text-red-600 text-xs">
        <FontAwesomeIcon icon={faSearch} class="w-3 h-3 mb-1" />
        <span>Search</span>
      </a>
      <div class="h-6 border-l border-gray-500"></div>
      <a
        href="tel:+916355467525"
        class="bg-green-500 text-white p-1 rounded-md flex items-center text-xs"
      >
        <FontAwesomeIcon icon={faPhone} class="w-3 h-3 mr-1" />
        WhatsApp Us
      </a>
    </div>
  </div>
</div>
<div
  style="height: 2rem;" class="flex w-full bg-white text-black items-center justify-between p-1 shadow-md h-8 md:h-12 lg:h-16"
>
  <ThirdNav />
</div>
<div class="flex w-full h-[1.5rem] overflow-hidden">
  <img src="/creditClock.jpg" alt="credit score" class="w-full py-0.5 h-auto object-cover"/>
</div>

<style>
  .top-8 {
    height: 2.5rem;
  }
  .h-10 {
    height: 2.5rem;
  }
  .h-6 {
    height: 1.5rem;
  }
  .w-6 {
    width: 1.5rem;
  }
  .w-5 {
    width: 1.25rem;
  }
  .w-3 {
    width: 0.75rem;
  }
  .p-1 {
    padding: 0.25rem;
  }
  .p-2 {
    padding: 0.5rem;
  }
  .ml-2 {
    margin-left: 0.5rem;
  }
  @media (max-width: 768px) {
    .hidden\:flex {
      display: none;
    }
    .flex {
      flex-direction: row;
      align-items: flex-end;
    }
    .w-full {
      width: 100%;
    }
    .h-12 {
      height: 3rem;
    }
    .p-0 {
      padding: 0.5rem;
    }
    .space-x-2 > :not([hidden]) ~ :not([hidden]) {
      --tw-space-x-reverse: 0;
      margin-right: calc(0.5rem * var(--tw-space-x-reverse));
      margin-left: calc(0.5rem * calc(1 - var(--tw-space-x-reverse)));
    }
  }
</style>
