<script setup lang="ts">
import { ref, onMounted } from 'vue';
import type { Ref } from 'vue'
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiViewDashboard, mdiTable, mdiTextBoxEdit, mdiAccountCircle, mdiLock } from '@mdi/js';

const dashboard = mdiViewDashboard;
const tables = mdiTable;
const forms = mdiTextBoxEdit;
const profile = mdiAccountCircle;
const lock = mdiLock;

const isMobileView: Ref<boolean> = ref(false);

function onResize() {
  isMobileView.value = window.innerWidth < 600;
}

onMounted(() => {
  onResize();
  window.addEventListener('resize', onResize, { passive: true })
})
</script>

<template>
  <aside class="aside">
    <a v-if="isMobileView" class="navbar-item" href="https://bulma.io">
      <img src="https://bulma.io/images/bulma-logo.png" width="112" height="28">
    </a>
    <div v-else class="aside-title">Admin UI</div>
    <p class="menu-label">General</p>
    <ul class="menu-list">
      <li>
        <router-link to="/">
          <span><svg-icon type="mdi" :path="dashboard" class="icon"></svg-icon></span>
          <span class="menu-text"> Dashboard</span>
        </router-link>
      </li>
    </ul>

    <p class="menu-label">Examples</p>
    <ul class="menu-list">
      <li>
        <router-link to="/tables">
          <span><svg-icon type="mdi" :path="tables" class="icon"></svg-icon></span>
          <span class="menu-text"> Tables</span>
        </router-link>
      </li>
      <li>
        <router-link to="/forms">
          <span><svg-icon type="mdi" :path="forms" class="icon"></svg-icon></span>
          <span class="menu-text"> Forms</span>
        </router-link>
      </li>
      <li>
        <router-link to="/profile">
          <span><svg-icon type="mdi" :path="profile" class="icon"></svg-icon></span>
          <span class="menu-text"> Profile</span>
        </router-link>
      </li>
      <li>
        <router-link to="/login">
          <span><svg-icon type="mdi" :path="lock" class="icon"></svg-icon></span>
          <span class="menu-text"> Login</span>
        </router-link>
      </li>
    </ul>
  </aside>
</template>

<style scoped>
@media screen and (max-width: 768px) {
  .aside {
    width: 50px !important;
    overflow: auto;
  }

  .aside .menu-label {
    display: none !important;
  }

  .aside .menu-text {
    display: none !important;
  }
}

.aside {
  background-color: #2E323A;
  height: 100vh;
  width: 14rem;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 40;
}

.aside-title {
  background-color: #17191E;
  font-size: 17px;
  font-weight: 700;
  color: #ffffff;
  padding: 1rem;
}

.aside .menu-label {
  padding: 0.75rem;
}

.aside .menu-list span {
  color: #9da3b1;
}

.aside .menu-list a {
  display: inline-flex;
  width: 100%;
  gap: 10px;
}

.aside .menu-list a:hover {
  background-color: #282C33;
}

.aside .menu-list a:hover > span {
  color: #ffffff;
}

.aside .menu-list a.router-link-exact-active {
  background-color: #282C33;
}

.aside .menu-list a.router-link-exact-active > span {
  color: #ffffff
}

.icon {
  width: 18px;
  height: 18px;
}
</style>