<template>
    <div id="movie-filter">
            <h2>Filter Result<h2>
                <h3>By Time of Day</h3>
            <div class="filter-group">
                    <CheckFilter v-for="time in times" category="time" v-bind:title="time" v-on:check-filter="checkFilter">
                    </CheckFilter>
            </div>
                <h3>By Genre</h3>
                <div class="filter-group">
                    <CheckFilter v-for="genre in genres" category="genre" v-bind:title="genre" v-on:check-filter="checkFilter">
                    </CheckFilter>
                </div>
    </div>
</template>

<script>
    import genres from "../util/genres"
    import times from "../util/times"
    import CheckFilter from "../components/CheckFilter.vue"

    export default {
        data() {
            return {
                genres,
                times
            }
        },
        components: {
            CheckFilter
        },

        methods: {
            checkFilter(category, title, checked) {
                this.$emit('check-filter', category, title, checked)
            }
        },
    }
</script>

