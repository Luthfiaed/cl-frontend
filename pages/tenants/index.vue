<template>
    <div class="container w-1/2 mx-auto mt-8">

    <div id="modal1" class="flex items-center justify-center fixed left-0 bottom-0 w-full h-full bg-gray-800" v-if="showModal">
        <div class="bg-white rounded-lg w-1/2">
            <div class="flex flex-col items-start p-4">
                <div class="flex items-center w-full">
                    <div class="text-gray-900 font-medium text-lg">Confirm delete</div>
                </div>
                <hr>
                <div class="">Are you sure you want to delete?</div>
                <hr>
                <div class="ml-auto">
                    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="confirmDelete(tenantId)">
                        Delete
                    </button>
                    <button
                    @click = "showModal = false"
                    class="bg-transparent hover:bg-gray-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded">
                        Cancel
                    </button>
                </div>
            </div>
        </div>
    </div>
        <div class="w-3/4 mr-6">
            <h3 class="text-2xl text-gray-900 my-2">Tenant List</h3>
            <nuxt-link
              :to="'/tenants/create'"
              rel="noopener noreferrer"
              class="button--blue-2"
              >
              Create New
            </nuxt-link>
        </div>
        <div class="grid grid-rows-1">
            <div v-for="tenant in tenants" :key="tenant.id">
            <!-- <img :src="$axios.defaults.baseURL + '/' + tenant.pic" />  seandainya ada gambarnya-->
                <div
                    class="w-full border border-gray-400 bg-white rounded px-4 py-5 my-3 flex flex-col justify-between leading-normal"
                >
                <div class="flex">
                    <div class="w-3/4">
                        <nuxt-link
                         :to="'/tenants/' + tenant.id"
                        >
                        <h4 class="underline">{{ tenant.tenant_name }}</h4>
                        </nuxt-link>
                    </div>
                    <div class="w-1/4 text-right">
                        <nuxt-link
                        :to="'/tenants/' + tenant.id + '/update'"
                        rel="noopener noreferrer"
                        class="button--blue-2"
                        >
                        Edit
                        </nuxt-link>
                    </div>
                    <div class="w-1/4 text-right">
                        <button
                        @click="showModal = true; sendData(tenant.id)"
                        class="button--red"
                        >
                        Delete
                        </button>
                    </div>
                </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    layout: 'minimal',

    data () {
        return {
            showModal: false
        }
    },

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
        },

        sendData(id) {
            this.tenantId = id
        },

        async confirmDelete(id) {
            try {
              let result = await this.$axios.$delete('tenants/' + id)
              console.log(result)
              location.reload()
            } 
            catch(error) {
              console.log(error)
            }
        }
    }
}
</script>