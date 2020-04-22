<template>
    <div>
        <h1>Admin-Home</h1>
        <p>{{ account }}</p>
    </div>
</template>

<script>
    import { mapState } from 'vuex'

    export default {
        data () {
            return {
                test: "test",
            }
        },
        computed: {
            ...mapState(['account'])
        }
    }
</script>