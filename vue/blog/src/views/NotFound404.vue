<template>
  <div>
    <h1>404</h1>
    <h1>This Page is Not Found!</h1>
    <b-button @click="goBackHome">Go Back</b-button>
  </div>
</template>

<script>
    export default {
        methods: {
            goBackHome: function() {
                this.$router.push({name:'Home'})
            }
        }
    }
</script>