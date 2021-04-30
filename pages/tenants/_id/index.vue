<template>
      <section class="container relative">
        <div class="flex absolute top-4">
          <div class="text-right">
            <nuxt-link
              :to="{ name: 'tenants-id-update',
                     params: { id: tenant.id }
                     }"
              class="button--blue-2 mb-2"
            >
              Edit
            </nuxt-link>
          </div>
        </div>
        <div class="block mb-2">
          <div class="w-full lg:max-w-full lg:flex">
            <div
              class="border border-gray-400 bg-white rounded p-8 flex flex-col justify-between leading-normal"
            >
              <div>
                <div class="text-gray-900 font-bold text-xl mb-2">
                  {{ tenant.tenant_name }}
                </div>
                <p class="text-sm font-bold flex mb-1">
                  API ID
                </p>
                <p class="text-gray-700 flex mb-3">
                  {{ tenant.api_id }}
                </p>
                <p class="text-sm font-bold flex items-center mb-1">
                  API KEY
                </p>
                <p class="text-gray-700 flex mb-3">
                  {{ tenant.api_key }}
                </p>
                <p class="text-sm font-bold flex items-center mb-1">
                  API URI
                </p>
                <p class="text-gray-700 flex mb-2">
                  {{ tenant.api_uri }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>
</template>

<script>
export default {
  layout: 'minimal',
  
  async asyncData({ $axios, params }) {
    const tenant = await $axios.$get('tenants/' + params.id)

    return { tenant }
  }
}
</script>

<style scoped>
.edit-button {
  position: absolute;
  left: 50px;
}

.container {
  width: 80%;
}
</style>