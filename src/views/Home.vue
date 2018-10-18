<template>
    <div v-if="user">
        <!-- <h1>Hello!</h1>
        <p>What you want to do?</p>
        <router-link to="/auth">Sign in</router-link> -->
        <div>{{user.email}}</div>
    </div>
</template>

<script>
    import auth from '@/auth'

    export default {
        name: 'home',
        computed: {
            user() {
                return this.$store.getters['user/user']
            }
        },
        methods: {
            logOut() {
                auth.logout()
            }
        }
    }
</script>

<style scoped>

</style>
