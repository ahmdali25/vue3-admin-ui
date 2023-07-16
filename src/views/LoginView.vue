<script setup lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiAccount, mdiLock } from '@mdi/js';
import { useRouter } from 'vue-router';
import { ref } from 'vue';

const account = mdiAccount;
const lock = mdiLock;

const router = useRouter();

const user = ref({
	email: "",
	password: ""
})

function toDashboard() {
	console.log(user);
	if (user.value.email != "" && user.value.password != "") {
		router.push('/');
	}
}
</script>

<template>
  <main>
    <section class="hero is-fullheight">
      <div class="hero-body">
        <div class="container">
          <div class="columns is-centered">
           <div class="column is-one-third">
						<div class="card">
              <header class="card-header">
            		<p class="card-header-title is-flex is-justify-content-center">
                  Login Admin
                </p>
              </header>
							<div class="card-content">
								<div class="field">
									<label class="label">Email</label>
									<div class="control has-icons-left">
										<input class="input" type="text" v-model="user.email" placeholder="">
										<span class="icon is-small is-left">
											<svg-icon type="mdi" :path="account"></svg-icon>
										</span>
									</div>
								</div>
								<div class="field">
									<label class="label">Password</label>
									<div class="control has-icons-left">
										<input class="input" type="password" v-model="user.password" placeholder="">
										<span class="icon is-small is-left">
											<svg-icon type="mdi" :path="lock"></svg-icon>
										</span>
									</div>
								</div>

								<hr class="divider">

								<div class="is-flex is-justify-content-center">
									<button @click="toDashboard" class="button is-info">Login</button>
								</div>
							</div>
            </div>
					 </div>
          </div>
        </div>
      </div>
  	</section>
  </main>
</template>

<style scoped>
main {
  background-color: #F8F8F8;
}

.divider {
	margin-left: -1.5rem;
	margin-right: -1.5rem;
}
</style>