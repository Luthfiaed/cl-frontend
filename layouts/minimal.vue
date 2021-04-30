<template>
  <div>
    <div class="flex flex-row flex-wrap flex-1 flex-grow pl-16 content-end">

        <div class="h-40 lg:h-20 w-full flex flex-wrap">
            <nav id="header1" class="bg-gray-100 w-auto flex-1 border-b-1 border-gray-300 order-1 lg:order-2">

                <div class="flex h-full justify-between items-center">
                    <div class="flex relative inline-block pr-6">

                        <div class="relative text-sm">
                            <button id="userButton" class="flex items-center focus:outline-none mr-3">
                                <img class="w-8 h-8 rounded-full mr-4" src="http://i.pravatar.cc/300" alt="Avatar of User"> <span class="hidden md:inline-block">Hi, User </span>
                                <svg class="pl-2 h-2" version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 129 129" xmlns:xlink="http://www.w3.org/1999/xlink" enable-background="new 0 0 129 129">
                                    <g>
                                        <path d="m121.3,34.6c-1.6-1.6-4.2-1.6-5.8,0l-51,51.1-51.1-51.1c-1.6-1.6-4.2-1.6-5.8,0-1.6,1.6-1.6,4.2 0,5.8l53.9,53.9c0.8,0.8 1.8,1.2 2.9,1.2 1,0 2.1-0.4 2.9-1.2l53.9-53.9c1.7-1.6 1.7-4.2 0.1-5.8z"></path>
                                    </g>
                                </svg>
                            </button>
                            <div id="userMenu" class="bg-white nunito rounded shadow-md mt-2 absolute mt-12 top-0 right-0 min-w-full overflow-auto z-30 invisible">
                                <ul class="list-reset">
                                    <li><a href="#" class="px-4 py-2 block text-gray-900 hover:bg-indigo-400 hover:text-white no-underline hover:no-underline">My account</a></li>
                                    <li><a href="#" class="px-4 py-2 block text-gray-900 hover:bg-indigo-400 hover:text-white no-underline hover:no-underline">Notifications</a></li>
                                    <li>
                                        <hr class="border-t mx-2 border-gray-400">
                                    </li>
                                    <li><a href="#" class="px-4 py-2 block text-gray-900 hover:bg-indigo-400 hover:text-white no-underline hover:no-underline">Logout</a></li>
                                </ul>
                            </div>
                        </div>

                    </div>

                    <!-- / Menu -->

                </div>

            </nav>
        </div>

    </div>

    <div id="sidebar" class="h-screen w-16 menu bg-white text-white px-4 flex items-center nunito static fixed shadow">

        <ul class="list-reset ">
            <li class="my-2 md:my-0 ">
                <nuxt-link to="/tenants" class="block py-1 md:py-3 pl-1 align-middle text-gray-600 no-underline hover:text-indigo-400">
                    <i class="fas fa-tasks fa-fw mr-3"></i><span class="w-full inline-block pb-1 md:pb-0 text-sm">Tenant</span>
                </nuxt-link>
            </li>
            <li class="my-2 md:my-0">
                <nuxt-link to="/" class="block py-1 md:py-3 pl-1 align-middle text-gray-600 no-underline hover:text-indigo-400">
                    <i class="fas fa-chart-area fa-fw mr-3 text-indigo-400"></i><span class="w-full inline-block pb-1 md:pb-0 text-sm">Report</span>
                </nuxt-link>
            </li>
        </ul>

    </div>
    <Nuxt />
  </div>
</template>

<style>
    .nunito {
        font-family: 'nunito', font-sans;
    }
        
    .border-b-1 {
        border-bottom-width: 1px;
    }
        
    .border-l-1 {
        border-left-width: 1px;
    }
        
    hover\:border-none:hover {
        border-style: none;
    }
        
    #sidebar {
        transition: ease-in-out all .3s;
        z-index: 9999;
    }
        
    #sidebar span {
        opacity: 0;
        position: absolute;
        transition: ease-in-out all .1s;
    }
        
    #sidebar:hover {
        width: 150px;
        box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
        /*shadow-2xl*/
    }
        
    #sidebar:hover span {
        opacity: 1;
    }
</style>