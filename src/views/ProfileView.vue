<script setup lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiAccount, mdiAccountCircle, mdiAccountEdit, mdiLock, mdiUpload } from '@mdi/js';
import BaseBreadcrumb from '@/components/BaseBreadcrumb.vue';
import BaseHeroTitle from '@/components/BaseHeroTitle.vue';
import { ref } from 'vue';

const account = mdiAccount;
const accountEdit = mdiAccountEdit;
const file = mdiUpload;
const lock = mdiLock;

const user = ref({
	name: "John Doe",
	email: "johndoe@example.com",
	profile: mdiAccountCircle,
	currentPassword: "",
	newPassword: "",
	confirmPassword: "",
})
</script>

<template>
  <div class="main">
    <BaseBreadcrumb level="Profile"/>
    <BaseHeroTitle title="Profile"/>
    <section class="columns mt-5">
      <div class="column">
				<div class="card">
					<header class="card-header">
						<p class="card-header-title">
							<svg-icon type="mdi" :path="accountEdit" class="icon mr-2"></svg-icon>
							Edit Profile
						</p>
					</header>
					<div class="card-content">
						<form>
							<div class="field is-horizontal">
								<div class="field-label is-normal">
									<label class="label">Avatar</label>
								</div>
								<div class="field-body">
									<div class="file is-primary">
										<label class="file-label">
											<input class="file-input" type="file" name="avatar" accept="image/png, image/jpeg">
											<span class="file-cta">
												<span class="file-icon">
													<svg-icon type="mdi" :path="file" class="icon"></svg-icon>
												</span>
												<span class="file-label">
													Pick a file
												</span>
											</span>
										</label>
									</div>
								</div>
							</div>

							<div class="field is-horizontal mt-5">
								<div class="field-label is-normal">
									<label class="label">Name</label>
								</div>
								<div class="field-body">
									<div class="field">
										<div class="control">
											<input class="input" type="text" placeholder="Name" v-model="user.name" required>
										</div>
									</div>
								</div>
							</div>

							<div class="field is-horizontal mt-5">
								<div class="field-label is-normal">
									<label class="label">Email</label>
								</div>
								<div class="field-body">
									<div class="field">
										<div class="control">
												<input class="input" type="email" placeholder="Email" v-model="user.email" required>
										</div>
									</div>
								</div>
							</div>
							<div class="card-footer mt-5">
								<div class="card-footer-items">
									<button type="submit" class="button is-info">Submit</button>
									<button type="reset" class="button is-info is-light">Reset</button>
								</div>
							</div>
						</form>
					</div>
					
				</div>
			</div>
			<div class="column">
				<div class="card">
					<header class="card-header">
						<p class="card-header-title">
							<svg-icon type="mdi" :path="account" class="icon mr-2"></svg-icon>
							Profile
						</p>
					</header>

					<div class="card-content">
						<div class="field-profile">
							<svg-icon type="mdi" :path="user.profile" class="icon-profile"></svg-icon>
						</div>
						<hr class="divider">
						<div class="field">
							<div class="label">
								<label class="label">Name</label>
							</div>
							<div class="field-body">
								<div class="field-user">
									<p>{{ user.name }}</p>
								</div>
							</div>
						</div>

						<div class="field">
							<div class="label">
								<label class="label">Email</label>
							</div>
							<div class="field-body">
								<div class="field-user">
									<p>{{ user.email }}</p>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
    </section>
		<section>
			<div class="card">
				<header class="card-header">
					<p class="card-header-title">
						<svg-icon type="mdi" :path="lock" class="icon mr-2"></svg-icon>
						Change Password
					</p>
				</header>
				<div class="card-content">
					<form>
						<div class="field is-horizontal mt-4">
							<div class="field-label is-normal">
								<label class="label">Current Password</label>
							</div>
							<div class="field-body">
								<div class="field">
									<div class="control">
										<input class="input" type="password" placeholder="" v-model="user.currentPassword" required>
									</div>
								</div>
							</div>
						</div>

						<hr class="divider">

						<div class="field is-horizontal mt-4">
							<div class="field-label is-normal">
								<label class="label">New Password</label>
							</div>
							<div class="field-body">
								<div class="field">
									<div class="control">
										<input class="input" type="password" placeholder="" v-model="user.newPassword" required>
									</div>
								</div>
							</div>
						</div>

						<div class="field is-horizontal">
							<div class="field-label is-normal">
								<label class="label">Confirm Password</label>
							</div>
							<div class="field-body">
								<div class="field">
									<div class="control">
										<input class="input" type="password" placeholder="" v-model="user.confirmPassword" required>
									</div>
								</div>
							</div>
						</div>

						<hr class="divider">

						<div class="field is-horizontal mt-4">
							<div class="field-label is-normal"></div>
							<div class="field-body">
								<div class="field">
									<button type="submit" class="button is-info">Submit</button>
								</div>
							</div>
						</div>
					</form>
				</div>
			</div>
		</section>
  </div>
</template>

<style scoped>
.card-footer-items {
	display: flex;
	gap: 10px;
	padding: 1.5rem 5rem;
}

.field-profile {
	display: flex;
	justify-content: center;
}

.field-user {
	height: 1.4rem;
}

.icon-profile {
	width: 7rem;
	height: 7rem;
}
</style>