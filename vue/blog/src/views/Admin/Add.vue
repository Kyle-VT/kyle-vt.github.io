<template>
    <div>
        <h1>Here is Add Page</h1>
        <p>{{ thisAccount }}</p>
    </div>
</template>

<script>
    import { mapState } from 'vuex'

    export default {
        mounted () {
            // this.thisAccount = this.$store.state.account
            // this.$store.state.account = "KyleChuang"
            const account = this.$store.state.account
            this.thisAccount = Object.assign({}, account)
        },
        data () {
            return {
                thisAccount: null,
            }
        },
        methods: {

        },
        computed: {
            ...mapState(['account'])
        }
    }
</script>