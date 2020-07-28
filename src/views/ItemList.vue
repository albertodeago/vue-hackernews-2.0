<template>
    <div class="items">
        <li class="item" v-for="item in items" :key="item.id">
            {{ item }}
        </li>
    </div>
</template>

<script>
export default {
    name: "item-list",
    data: () => ({

    }),

    // Server-side only
    // This will be called by the server renderer automatically
    serverPrefetch () {
        // return the Promise from the action
        // so that the component waits before rendering
        console.log("server prefetch");
        return this.fetchItems()
    },

    computed: {
        items() {
            return this.$store.state.itemList;
        }
    },

    methods: {
        fetchItems() {
            // return the Promise from the action
            return this.$store.dispatch('fetchItems');
        }
    }
}
</script>

<style>

</style>