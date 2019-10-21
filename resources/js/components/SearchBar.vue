<template>
    <div>
        <input type="text" placeholder="Search..." id="searchTerm" v-model="searchTerm" @input="search">
    </div>
</template>

<script>
    export default {
        name: "SearchBar",

        data: function () {
            return {
                searchTerm: ''
            }
        },

        methods: {
            search: function () {
                axios.post('/api/search', {searchTerm: this.searchTerm})
                    .then(response => {
                        console.log(response.data);
                    })
                    .catch(error => {

                    });
            }
        }
    }
</script>

<style scoped>

</style>
