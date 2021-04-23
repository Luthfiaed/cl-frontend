<template>
  <div class="container mx-auto mt-20">
    <div class="flex justify-between items-center">
      <div class="w-full border border-gray-400 bg-white rounded pl-8 pr-8 pt-8 pb-4 flex flex-col justify-between leading-normal">
        <div class="mx-auto">
          <div class="flex">
          <h1 class="title mb-4">
            Confirm Delete Tenant {{ tenant.tenant_name }}
          </h1>
          </div>
          <div class="links w-1/2 mx-auto">
            <button
              @click="deleteTenant"
              class="button--red">
              Yes
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    async asyncData({ $axios, params }) {
        const tenant = await $axios.$get('tenants/' + params.id)
        return { tenant }
    },

    methods: {
      async deleteTenant() {
        try {
          let result = await this.$axios.$delete('tenants/' + this.$route.params.id)
          this.$router.push({
                    name: 'tenants'
                })
          console.log(result)
        }
        catch(error) {
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