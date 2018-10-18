<template>
    <div class="">
        <section>
            <div class="block">
                <button class="button" @click="activeTab = 1">Set Music</button>
            </div>
            <div class="block">
                <b-switch v-model="showBooks"> Show Books item </b-switch>
            </div>
            <b-tabs v-model="activeTab">
                <b-tab-item label="Pictures">
                    Lorem ipsum dolor sit amet.
                </b-tab-item>

                <b-tab-item label="Music">
                    Lorem <br>
                    ipsum <br>
                    dolor <br>
                    sit <br>
                    amet.
                </b-tab-item>

                <b-tab-item :visible="showBooks" label="Books">
                    What light is light, if Silvia be not seen? <br>
                    What joy is joy, if Silvia be not by— <br>
                    Unless it be to think that she is by <br>
                    And feed upon the shadow of perfection? <br>
                    Except I be by Silvia in the night, <br>
                    There is no music in the nightingale.
                </b-tab-item>

                <b-tab-item label="Videos" disabled>
                    Nunc nec velit nec libero vestibulum eleifend.
                    Curabitur pulvinar congue luctus.
                    Nullam hendrerit iaculis augue vitae ornare.
                    Maecenas vehicula pulvinar tellus, id sodales felis lobortis eget.
                </b-tab-item>
            </b-tabs>
        </section>
        <div v-if="user">
            <!-- <h1>Hello!</h1>
            <p>What you want to do?</p>
            <router-link to="/auth">Sign in</router-link> -->
            <div>{{user.email}}</div>
            sdfsdfds
        </div>
    </div>
    
</template>

<script>
    import auth from '@/auth'

    export default {
        name: 'home',
        data() {
            return {
                activeTab: 0,
                showBooks: false
            }
        },
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
