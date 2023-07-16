<script setup lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiAccount, mdiEmail, mdiInformation } from '@mdi/js';
import BaseBreadcrumb from '@/components/BaseBreadcrumb.vue';
import BaseHeroTitle from '@/components/BaseHeroTitle.vue';

const account = mdiAccount;
const email = mdiEmail;
const info = mdiInformation;
</script>


<template>
  <div class="main">
    <BaseBreadcrumb level="Forms"/>
    <BaseHeroTitle title="Forms"/>
    <section class="card mt-5">
      <header class="card-header">
        <p class="card-header-title">
          Forms
        </p>
      </header>
      <div class="card-content">
        <form>
          <div class="field">
            <label class="label">Name</label>
            <div class="control has-icons-left has-icons-right">
              <input class="input" type="text" placeholder="Name" value="" required>
              <span class="icon is-small is-left">
                <svg-icon type="mdi" :path="account"></svg-icon>
              </span>
              <span class="icon is-small is-right">
                <i class="fas fa-check"></i>
              </span>
            </div>
          </div>

          <div class="field">
            <label class="label">Email</label>
            <div class="control has-icons-left has-icons-right">
              <input class="input" type="email" placeholder="Email" value="" required>
              <span class="icon is-left">
                <svg-icon type="mdi" :path="email"></svg-icon>
              </span>
              <span class="icon is-small is-right">
                <svg-icon type="mdi" :path="info"></svg-icon>
              </span>
            </div>
          </div>

          <div class="field">
            <label class="label">Phone Number</label>
            <div class="field-body">
              <div class="field is-expanded">
                <div class="field has-addons">
                  <p class="control">
                    <a class="button is-static">
                      +62
                    </a>
                  </p>
                  <p class="control is-expanded">
                    <input class="input" type="tel" placeholder="Your phone number" required>
                  </p>
                </div>
                <p class="help">Do not enter the first zero</p>
              </div>
            </div>
          </div>

          <div class="field">
            <label class="label">Department</label>
            <div class="control">
              <div class="select">
                <select>
                  <option>Business Development</option>
                  <option>Marketing</option>
                  <option>Sales</option>
                </select>
              </div>
            </div>
          </div>

          <div class="field">
            <label class="label">Subject</label>
            <div class="field-body">
              <div class="field">
                <div class="control">
                  <input class="input" type="text" placeholder="e.g. Partnership opportunity" required>
                </div>
              </div>
            </div>
          </div>

          <div class="field">
            <label class="label">Message</label>
            <div class="control">
              <textarea class="textarea" placeholder="Input a message" required></textarea>
            </div>
          </div>

          <div class="field is-grouped">
            <div class="control">
              <button type="submit" class="button is-info">Submit</button>
            </div>
            <div class="control">
              <button type="reset" class="button is-info is-light">Reset</button>
            </div>
          </div>
        </form>
      </div>
    </section>
  </div>
</template>