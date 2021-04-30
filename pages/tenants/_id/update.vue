<template>
    <section class="container relative">
        <div class="flex absolute top-4">
          <div class="w-3/4 mr-2 content-end">
            <h3 class="text-2xl text-gray-900 mb-4">Edit Tenant</h3>
          </div>
          <div class="w-1/4 content-end mb-5">
            <button
              @click="edit"
              class="button--blue-2 px-4 py-1 my-2 rounded inline-flex items-center">
              Save
            </button>
          </div>
        </div>
        <div class="block mb-2">
          <div class="w-full lg:max-w-full lg:flex mb-4">
            <div
              class="w-full border border-gray-400 bg-white rounded pl-8 pr-8 pt-8 pb-4 flex flex-col justify-between leading-normal"
            >
              <form class="w-full">
                <div class="flex flex-wrap -mx-3 mb-6">
                  <div class="w-full px-3">
                    <label
                      class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                    >
                      Tenant Name
                    </label>
                    <input
                      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                      type="text"
                      v-model="tenant.tenant_name"
                    />
                  </div>
                  <div class="w-full px-3">
                    <label
                      class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2 mt-3"
                    >
                      API ID
                    </label>
                    <input
                      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                      type="text"
                      v-model="tenant.api_id"
                    />
                  </div>
                  <div class="w-full px-3">
                    <label
                      class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2 mt-3"
                    >
                      API Key
                    </label>
                    <input
                      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                      type="text"
                      v-model="tenant.api_key"
                    />
                  </div>
                  <div class="w-full px-3">
                    <label
                      class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                    >
                      API URI
                    </label>
                    <input
                      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                      type="text"
                      v-model="tenant.api_uri"
                    />
                  </div>
                </div>
              </form>
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
    },

    methods: {
      async edit() {
        try {
          let response = await this.$axios.$put(
            'tenants/' + this.$route.params.id, 
            {
              tenant_name: this.tenant.tenant_name,
              api_id: this.tenant.api_id,
              api_key: this.tenant.api_key,
              api_uri: this.tenant.api_uri,
              tenant_domain: this.tenant.tenant_domain
            }
          )
          this.$router.push({
            name: 'tenants-id',
            params: { id: response.id }
            })
          console.log(response)
        } catch(error) {
          console.log(error)
        }
      }
    }
}
</script>

<style scoped>
.container {
    width: 80%;
}
</style>