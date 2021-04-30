<template>
  <div class="container">
    <div id="dash-content" class="bg-gray-200 py-6 lg:py-0 w-full lg:max-w-sm flex flex-wrap content-start">
      
      <div class="w-1/2 lg:w-full">
        <div class="border-2 border-gray-400 border-dashed hover:border-transparent hover:bg-white hover:shadow-xl rounded p-6 m-2 md:mx-10 md:my-6">
          <div class="flex flex-col items-center">
            <div class="flex-shrink pr-4">
              <div class="rounded-full p-3 bg-gray-300"><i class="fa fa-wallet fa-fw fa-inverse text-indigo-500"></i></div>
            </div>
            <div class="flex-1">
              <h3 class="font-bold text-3xl">732 <span class="text-green-500"><i class="fas fa-caret-up"></i></span></h3>
              <h5 class="font-bold text-gray-500">Total New License</h5>
            </div>
          </div>
        </div>
      </div>

      <div class="w-1/2 lg:w-full">
        <div class="border-2 border-gray-400 border-dashed hover:border-transparent hover:bg-white hover:shadow-xl rounded p-6 m-2 md:mx-10 md:my-6">
          <div class="flex flex-col items-center">
            <div class="flex-shrink pr-4">
              <div class="rounded-full p-3 bg-gray-300"><i class="fas fa-users fa-fw fa-inverse text-indigo-500"></i></div>
            </div>
            <div class="flex-1">
              <h3 class="font-bold text-3xl">9805 <span class="text-orange-500"><i class="fas fa-exchange-alt"></i></span></h3>
              <h5 class="font-bold text-gray-500">Total Active License</h5>
            </div>
          </div>
        </div>
      </div>

      <div class="w-1/2 lg:w-full">
        <div class="border-2 border-gray-400 border-dashed hover:border-transparent hover:bg-white hover:shadow-xl rounded p-6 m-2 md:mx-10 md:my-6">
          <div class="flex flex-col items-center">
            <div class="flex-shrink pr-4">
              <div class="rounded-full p-3 bg-gray-300"><i class="fas fa-user-plus fa-fw fa-inverse text-indigo-500"></i></div>
            </div>
            <div class="flex-1">
              <h3 class="font-bold text-3xl">15 <span class="text-yellow-600"><i class="fas fa-caret-up"></i></span></h3>
              <h5 class="font-bold text-gray-500">Total Tenant</h5>
            </div>
          </div>
        </div>
      </div>

    </div>

    <div class="p-3">

      <div class="border-b p-3">
        <h5 class="font-bold text-black">License Report</h5>
      </div>
      
      <div class="p-5">
        <table class="w-full p-5 text-gray-700">
          <thead>
            <tr>
              <th class="text-left text-blue-900">Tenant Name</th>
              <th></th>
              <th class="text-left text-blue-900">This Month</th>
              <th></th>
              <th class="text-left text-blue-900">Today</th>
              <th></th>
              <th class="text-left text-blue-900">Last Month</th>
              <th></th>
              <th class="text-left text-blue-900">Growth</th>
            </tr>
          </thead>

          <tbody>
            <tr v-for="license in licenses" :key="license.TenantName" >
              <td class="text-left">{{ license.TenantName }}</td>
              <th></th>
              <td class="text-left">{{ license.ThisMonth }}</td>
              <th></th>
              <td class="text-left">{{ license.Today }}</td>
              <td></td>
              <td class="text-left">{{ license.LastMonth }}</td>
              <td></td>
              <td class="text-left">{{ license.Growth }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  layout: 'minimal',

  async asyncData({ $axios }) {
    const licenses = await $axios.$get('licenses/email')
    return { licenses }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

table tr th:empty, td:empty {
  width: 30px;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Poppins',
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 64px;
  color: #2354a1;
  letter-spacing: 1px;
  margin-bottom: 20px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
