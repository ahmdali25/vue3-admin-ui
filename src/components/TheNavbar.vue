<template>
    <nav class="navbar is-fixed-top" role="navigation" aria-label="main navigation" id="navbar">
        <div class="navbar-brand">
            <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
            </a>
        </div>

        <div id="navbarBasicExample" class="navbar-menu">
            <div class="navbar-end">
                <div class="navbar-item has-dropdown is-hoverable">
                    <a class="navbar-link">
                        <svg-icon type="mdi" :path="accountCircle" class="account-circle"></svg-icon>
                        &nbsp; John Doe
                    </a>

                    <div class="navbar-dropdown">
                        <a class="navbar-item">
                            <svg-icon type="mdi" :path="account"></svg-icon>
                            &nbsp; Profile
                        </a>
                        <hr class="navbar-divider">
                        <a class="navbar-item">
                            <svg-icon type="mdi" :path="logout"></svg-icon>
                            &nbsp; Logout
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script setup lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiAccountCircle, mdiAccount, mdiLogout } from '@mdi/js';

const account = mdiAccount;
const accountCircle = mdiAccountCircle;
const logout = mdiLogout;
</script>

<style scoped>
#navbar {
    margin: 0;
    height: 80px;
}
.account-circle {
    width: 40px !important;
    height: 40px !important;
}
</style>