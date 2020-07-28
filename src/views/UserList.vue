<template>
    <div class="users">
        <li class="user" v-for="user in users" :key="user.id">
            {{ user }}
        </li>
    </div>
</template>

<script>
export default {
    name: "user-list",
    data: () => ({

    }),

    // Server-side only
    // This will be called by the server renderer automatically
    serverPrefetch () {
        // return the Promise from the action
        // so that the component waits before rendering
        console.log("Fetching users")
        return this.fetchUsers()
    },

    computed: {
        users() {
            return this.$store.state.userList;
        }
    },

    methods: {
        fetchUsers() {
            // return the Promise from the action
            return this.$store.dispatch('fetchUsers');
        }
    }
}
</script>

<style lang="scss">

</style>