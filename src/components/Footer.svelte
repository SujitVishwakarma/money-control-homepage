<script>
  import {
    faFacebook,
    faInstagram,
    faTwitter,
    faTelegram,
  } from "@fortawesome/free-brands-svg-icons";
  import { FontAwesomeIcon } from "@fortawesome/svelte-fontawesome";
  import { faStar } from "@fortawesome/free-solid-svg-icons";
</script>

<footer class="bg-pink-100 text-gray-700 py-2 mt-8">
  <div class="container mx-auto px-4">
    <div class="flex flex-wrap justify-center sm:justify-between text-center sm:text-left">
      <div class="w-full sm:w-1/2 lg:w-1/4 mb-6 flex flex-col items-center sm:items-start">
        <h2 class="font-semibold text-xl">Sachtak.com</h2>
        <div class="flex items-center mt-2">
          <span class="text-yellow-500">
            <FontAwesomeIcon icon={faStar} />
            <FontAwesomeIcon icon={faStar} />
            <FontAwesomeIcon icon={faStar} />
            <FontAwesomeIcon icon={faStar} />
            <FontAwesomeIcon icon={faStar} />
          </span>
        </div>
        <p class="mt-2">Overall client rating is 4.9 out of 8,500 Clients</p>
      </div>

      <div class="w-full sm:w-1/2 lg:w-1/4 mb-6 flex flex-col items-center sm:items-start">
        <h2 class="font-semibold text-xl hover:text-orange-500 hover:translate-x-2">Follow Us</h2>
        <ul class="mt-2 space-y-2">
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            <FontAwesomeIcon icon={faFacebook} class="mr-2 " />
            Facebook
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            <FontAwesomeIcon icon={faInstagram} class="mr-2" />
            Instagram
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            <FontAwesomeIcon icon={faTwitter} class="mr-2" />
            Twitter
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            <FontAwesomeIcon icon={faTelegram} class="mr-2" />
            Telegram
          </li>
        </ul>
      </div>
      <!-- second one  -->
      <div class="w-full sm:w-1/2 lg:w-1/4 mb-6 flex flex-col items-center sm:items-start">
        <h2 class="font-semibold text-xl hover:text-orange-500 hover:translate-x-2">Industries</h2>
        <ul class="mt-2 space-y-2 ">
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            Health Care
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            Education
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            Retail
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            Music & Video
          </li>
        </ul>
      </div>
      <!-- Third one  -->
      <div class="w-full sm:w-1/2 lg:w-1/4 mb-6 flex flex-col items-center sm:items-start">
        <h2 class="font-semibold text-xl hover:text-orange-500 hover:translate-x-2">Services</h2>
        <ul class="mt-2 space-y-2">
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            Web Development
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            App Development
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            Web Design
          </li>
          <li class="flex items-center justify-center sm:justify-start hover:text-blue-500">
            Social Media Marketing
          </li>
        </ul>
      </div>
    </div>
  </div>
  <!-- copy right section  -->
  <div class="text-center mt-8">
    <p>
      Copyright © 2024. All rights reserved. Template By Sujit
      Vishwakarma
    </p>
  </div>
</footer>
