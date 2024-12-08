<script>
  import { faHome, faVideo, faStar, faNewspaper, faBars } from "@fortawesome/free-solid-svg-icons";
  import { FontAwesomeIcon } from "@fortawesome/svelte-fontawesome";
  import SideBar from "./SideBar.svelte";
</script>

<div class="fixed bottom-0 left-0 right-0 bg-white shadow-md lg:hidden flex justify-around items-center py-0.5">
  <a href="#" class="flex flex-col items-center">
    <FontAwesomeIcon icon={faHome} class="w-6 h-6 text-red-600" />
    <span class="text-sm">Home</span>
  </a>
  <a href="#" class="flex flex-col items-center">
    <FontAwesomeIcon icon={faVideo} class="w-6 h-6" />
    <span class="text-sm">Live TV</span>
  </a>
  <a href="#" class="flex flex-col items-center">
    <FontAwesomeIcon icon={faStar} class="w-6 h-6" />
    <span class="text-sm">Personalise</span>
  </a>
  <a href="#" class="flex flex-col items-center">
    <FontAwesomeIcon icon={faNewspaper} class="w-6 h-6" />
    <span class="text-sm">Magazine</span>
  </a>
  <div class="flex items-center space-x-2">
    <div class="drawer">
      <input id="my-drawer" type="checkbox" class="drawer-toggle" />
      <div class="drawer-content p-0">
        <!-- Page content here -->
        <label for="my-drawer" class="btn flex-col bg-white text-black border-none hover:bg-slate-50 p-0">
          <FontAwesomeIcon icon={faBars} class="mr-2" />
          <span>Menu</span>
        </label>
      </div>
      <div class="drawer-side">
        <label for="my-drawer" aria-label="close sidebar" class="drawer-overlay"></label>
        <ul class="menu bg-base-200 text-base-content min-h-full w-60 p-4 flex justify-between" style="margin-top: 150px;">
          <!-- Sidebar content here -->
          <li><SideBar /></li>
        </ul>
      </div>
    </div>
  </div>
</div>

<style>
  .drawer-content {
    padding: 0;
  }
  .drawer-toggle {
    display: none;
  }
  .drawer-side {
    width: 60%;
  }
</style>
