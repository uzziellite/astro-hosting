<script>
  import {clickOutside} from "@directives/click_outside.js"

  let servicesActive = false
  let domainsActive = false
  let mobileMenuActive = false
  const name = import.meta.env.PUBLIC_NAME
</script>

<div class="fixed w-full top-0 z-50 bg-white border-b border-sky-600 shadow-md">
  <div class="mx-auto max-w-7xl px-4 sm:px-6">
    <div class="flex items-center justify-between border-b-2 border-gray-100 py-6 md:justify-start md:space-x-10">
      <div class="flex justify-start lg:w-0 lg:flex-1">
        <a href="/">
          <span class="sr-only">{name}</span>
          <img class="h-8 w-auto sm:h-10" src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600" alt={name}>
        </a>
      </div>
      <div class="-my-2 -mr-2 md:hidden">
        <button type="button" class="inline-flex items-center justify-center rounded-md bg-white p-2 hover:bg-gray-100 focus:outline-none" aria-expanded={`${mobileMenuActive ? 'true' : 'false'}`} on:click={() => mobileMenuActive = ! mobileMenuActive }>
          <span class="sr-only">Open menu</span>
          <!-- Heroicon name: outline/bars-3 -->
          <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
          </svg>
        </button>
      </div>
      <nav class="hidden space-x-10 md:flex">
        <div class="relative">
          <button type="button" class="group inline-flex items-center rounded-md bg-white text-base font-bold focus:outline-none" aria-expanded={`${servicesActive ? 'true' : 'false'}`} use:clickOutside on:outclick={() => servicesActive = false} on:click={() => servicesActive = ! servicesActive}>
            <span>Services</span>
            <!--
              Heroicon name: mini/chevron-down

              Item active: "text-gray-600", Item inactive: "text-gray-400"
            -->
            <svg class="ml-2 h-5 w-5 group-hover:text-gray-500" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
              <path fill-rule="evenodd" d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z" clip-rule="evenodd" />
            </svg>
          </button>

          <!--
            'Solutions' flyout menu, show/hide based on flyout menu state.

            Entering: "transition ease-out duration-200"
              From: "opacity-0 translate-y-1"
              To: "opacity-100 translate-y-0"
            Leaving: "transition ease-in duration-150"
              From: "opacity-100 translate-y-0"
              To: "opacity-0 translate-y-1"
          -->
          <div class={`absolute z-10 -ml-4 mt-3 w-screen max-w-md transform px-2 sm:px-0 lg:left-1/2 lg:ml-0 lg:-translate-x-1/2 ${servicesActive ? '' : 'hidden'}`}>
            <div class="overflow-hidden rounded-lg shadow-lg ring-1 ring-black ring-opacity-5">
              <div class="relative grid gap-6 bg-white px-5 py-6 sm:gap-8 sm:p-8">
                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: user-group -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Shared Hosting
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Get hosting for small and medium sized businesses at affordable prices
                    </p>
                  </div>
                </a>

                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/office-building -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Corporate Hosting
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Hosting specifically dedicated to the most demanding companies. Let us host your data because we are experts at it.
                    </p>
                  </div>
                </a>

                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/badge-check -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Dedicated Hosting
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Lease an entire server to utilize maximum resources for your specific use case.
                    </p>
                  </div>
                </a>

                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/server -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      VPS Hosting
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Mimic dedicated server environments within a shared environment. Gain root access and have the freedom to run your own applications
                    </p>
                  </div>
                </a>

                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/at-symbol -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 12a4 4 0 10-8 0 4 4 0 008 0zm0 0v1.5a2.5 2.5 0 005 0V12a9 9 0 10-9 9m4.5-1.206a8.959 8.959 0 01-4.5 1.207"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Emails
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Run and manage your own emails. 
                    </p>
                  </div>
                </a>
              </div>
            </div>
          </div>
        </div>


        <div class="relative">
          <button type="button" class="group inline-flex items-center rounded-md bg-white text-base font-bold focus:outline-none" aria-expanded={`${domainsActive ? 'true' : 'false'}`} use:clickOutside on:outclick={() => domainsActive = false} on:click={() => domainsActive = ! domainsActive}>
            <span>Domains</span>
            <!--
              Heroicon name: mini/chevron-down
            -->
            <svg class="ml-2 h-5 w-5 group-hover:text-gray-500" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
              <path fill-rule="evenodd" d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z" clip-rule="evenodd" />
            </svg>
          </button>

          <!--
            'More' flyout menu, show/hide based on flyout menu state.

            Entering: "transition ease-out duration-200"
              From: "opacity-0 translate-y-1"
              To: "opacity-100 translate-y-0"
            Leaving: "transition ease-in duration-150"
              From: "opacity-100 translate-y-0"
              To: "opacity-0 translate-y-1"
          -->
          <div class={`absolute left-1/2 z-10 mt-3 w-screen max-w-md -translate-x-1/2 transform px-2 sm:px-0 ${domainsActive ? '' : 'hidden'}`}>
            <div class="overflow-hidden rounded-lg shadow-lg ring-1 ring-black ring-opacity-5">
              <div class="relative grid gap-6 bg-white px-5 py-6 sm:gap-8 sm:p-8">
                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/globe-alt -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Register Domain
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Register a new domain for your business or personal use at affordable prices
                    </p>
                  </div>
                </a>

                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/dollar-symbol -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Domain Pricing
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Get more information about how we price our domains
                    </p>
                  </div>
                </a>

                <a href="/" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/arrow-left -->
                  <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"></path></svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Domain Transfer
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Transfer a domain to us. It is safe, fast and easy plus we will also help you to migrate your data
                    </p>
                  </div>
                </a>

                <a href="#" class="-m-3 flex items-start rounded-lg p-3 hover:bg-gray-50">
                  <!-- Heroicon name: outline/shield-check -->
                  <svg class="h-6 w-6 flex-shrink-0 text-indigo-600" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75m-3-7.036A11.959 11.959 0 013.598 6 11.99 11.99 0 003 9.749c0 5.592 3.824 10.29 9 11.623 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.598-3.751h-.152c-3.196 0-6.1-1.248-8.25-3.285z" />
                  </svg>
                  <div class="ml-4">
                    <p class="text-base font-medium text-gray-900">
                      Domain Security
                    </p>
                    <p class="mt-1 text-sm text-gray-500">
                      Determine the security of your domain. Find issues, warnings and complete information (standard procedures and best practices) regarding your domain's DNS. Also check your website's A record and MX record IP in blacklists.
                    </p>
                  </div>
                </a>
              </div>
            </div>
          </div>
        </div>
        <a href="/support" class="text-base font-bold">Support</a>
        <a href="/contact-us" class="text-base font-bold">Contact</a>
      </nav>
      <div class="hidden items-center justify-end md:flex md:flex-1 lg:w-0">
        <a href="/login" class="whitespace-nowrap text-base font-bold">Sign in</a>
        <a href="/register" class="ml-8 inline-flex items-center justify-center whitespace-nowrap rounded-md border border-transparent bg-sky-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-sky-700">Sign up</a>
      </div>
    </div>
  </div>

  <!--
    Mobile menu, show/hide based on mobile menu state.

    Entering: "duration-200 ease-out"
      From: "opacity-0 scale-95"
      To: "opacity-100 scale-100"
    Leaving: "duration-100 ease-in"
      From: "opacity-100 scale-100"
      To: "opacity-0 scale-95"
  -->
  <div class={`absolute inset-x-0 top-0 origin-top-right transform p-2 transition ${mobileMenuActive ? '' : 'hidden'}`} use:clickOutside on:outclick={() => mobileMenuActive = false}>
    <div class="divide-y-2 divide-gray-50 rounded-lg bg-white shadow-lg ring-1 ring-black ring-opacity-5">
      <div class="px-5 pt-5 pb-6">
        <div class="flex items-center justify-between">
          <div>
            <img class="h-8 w-auto" src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600" alt={name}>
          </div>
          <div class="-mr-2">
            <button type="button" class="inline-flex items-center justify-center rounded-md bg-white p-2 hover:bg-gray-100 focus:outline-none" on:click={() => mobileMenuActive = false}>
              <span class="sr-only">Close menu</span>
              <!-- Heroicon name: outline/x-mark -->
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>
          </div>
        </div>
        <div class="mt-6">
          <nav class="grid gap-y-8">
            <a href="/" class="-m-3 flex items-center rounded-md p-3 hover:bg-gray-50">
              <!-- Heroicon name: outline/server -->
              <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01"></path></svg>
              <span class="ml-3 text-base font-medium text-gray-900">
                Hosting
              </span>
            </a>

            <a href="/" class="-m-3 flex items-center rounded-md p-3 hover:bg-gray-50">
              <!-- Heroicon name: outline/at-symbol -->
              <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 12a4 4 0 10-8 0 4 4 0 008 0zm0 0v1.5a2.5 2.5 0 005 0V12a9 9 0 10-9 9m4.5-1.206a8.959 8.959 0 01-4.5 1.207"></path></svg>
              <span class="ml-3 text-base font-medium text-gray-900">
                Emails
              </span>
            </a>

            <a href="/" class="-m-3 flex items-center rounded-md p-3 hover:bg-gray-50">
              <!-- Heroicon name: outline/shield-check -->
              <svg class="h-6 w-6 flex-shrink-0 text-indigo-600" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75m-3-7.036A11.959 11.959 0 013.598 6 11.99 11.99 0 003 9.749c0 5.592 3.824 10.29 9 11.623 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.598-3.751h-.152c-3.196 0-6.1-1.248-8.25-3.285z" />
              </svg>
              <span class="ml-3 text-base font-medium text-gray-900">Security</span>
            </a>

            <a href="#" class="-m-3 flex items-center rounded-md p-3 hover:bg-gray-50">
              <!-- Heroicon name: outline/globe-alt -->
              <svg class="w-6 h-6 flex-shrink-0 text-indigo-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"></path></svg>
              <span class="ml-3 text-base font-medium text-gray-900">
                Domains
              </span>
            </a>
          </nav>
        </div>
      </div>
      <div class="space-y-6 py-6 px-5">
        <!--<div class="grid grid-cols-2 gap-y-4 gap-x-8">
          <a href="/" class="text-base font-medium text-gray-900 hover:text-gray-700">Pricing</a>

          <a href="/" class="text-base font-medium text-gray-900 hover:text-gray-700">Help Center</a>

          <a href="/" class="text-base font-medium text-gray-900 hover:text-gray-700">WHO IS</a>

          <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">Security</a>
        </div>-->
        <div>
          <a href="/register" class="flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-indigo-700">Sign up</a>
          <p class="mt-6 text-center text-base font-medium text-gray-500">
            Existing customer?
            <a href="/login" class="text-indigo-600 hover:text-indigo-500">Sign in</a>
          </p>
        </div>
      </div>
    </div>
  </div>
</div>
