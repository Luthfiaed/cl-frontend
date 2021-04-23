<template>
    <div class="container w-1/2 mx-auto mt-8">
        <div class="w-3/4 mr-6">
            <h3 class="text-2xl text-gray-900 my-2">List of Tenants</h3>
        </div>
        <div class="grid grid-rows-1">
            <div v-for="tenant in tenants" :key="tenant.id">
            <!-- <img :src="$axios.defaults.baseURL + '/' + tenant.pic" />  seandainya ada gambarnya-->
                <div
                    class="w-full border border-gray-400 bg-white rounded px-4 py-5 my-3 flex flex-col justify-between leading-normal"
                >
                <div class="flex">
                    <div class="w-3/4">
                        <h4>{{ tenant.tenant_name }}</h4>
                    </div>
                    <div class="w-1/4 text-right">
                        <nuxt-link
                        :to="'/tenants/' + tenant.id + '/update'"
                        target="_blank"
                        rel="noopener noreferrer"
                        class="button--blue-2"
                        >
                        Edit
                        </nuxt-link>
                    </div>
                    <div class="w-1/4 text-right">
                        <nuxt-link
                        :to="'/tenants/' + tenant.id + '/delete'"
                        target="_blank"
                        rel="noopener noreferrer"
                        class="button--red"
                        >
                        Delete
                        </nuxt-link>
                    </div>
                </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    async asyncData({ $axios }) {
        const tenants = await $axios.$get('tenants')
        return { tenants }
    },

    methods: {
        edit() {
            this.$router.push({
                name: 'tenants-id-update',
                params: { id: tenant.id }
            })
        }
    }
}
</script>