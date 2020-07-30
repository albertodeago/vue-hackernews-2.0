<template>
    <div class="users">
        <div class="pa-5">
            <v-btn color="success">Success</v-btn>
            <v-btn color="error">Error</v-btn>
            <v-btn color="warning">Warning</v-btn>
            <v-btn color="info">Info</v-btn>
        </div>
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