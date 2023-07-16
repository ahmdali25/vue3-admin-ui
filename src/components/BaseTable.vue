<script setup lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiPencil, mdiDelete } from '@mdi/js';
import { ref } from "vue";

const iconEdit = mdiPencil;
const iconDelete = mdiDelete;

const datas = ref([
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "Success", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "Pending", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "On Progress", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "On Progress", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "Success", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "Success", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "Pending", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "On Progress", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "On Progress", created: "July 16, 2023" },
  { name: "John Doe", company: "PT Maju Jaya Abadi", city: "Jakarta", status: "Success", created: "July 16, 2023" }
]);
</script>

<template>
    <div>
        <table class="table is-fullwidth is-hoverable is-striped mt-4">
            <thead>
                <tr>
                <th>Name</th>
                <th>Company</th>
                <th>City</th>
                <th>Status</th>
                <th>Created</th>
                <th>Action</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(data, index) in datas" :key="index">
                <td data-label="name">{{ data.name }}</td>
                <td data-label="company">{{ data.company }}</td>
                <td data-label="city">{{ data.city }}</td>
                <td data-label="status">
                    <span class="tag" :class="data.status == 'Success' ? 'is-success' : data.status == 'On Progress' ? 'is-info' : 'is-warning'">{{ data.status }}</span>
                </td>
                <td data-label="created">{{ data.created }}</td>
                <td>
                    <button class="button is-small is-info mr-2">
                    <svg-icon class="icon is-small" type="mdi" :path="iconEdit"></svg-icon>
                    </button>
                    <button class="button is-small is-danger">
                    <svg-icon class="icon is-small" type="mdi" :path="iconDelete"></svg-icon>
                    </button>
                </td>
                </tr>
            </tbody>
        </table>
        <nav class="pagination" role="navigation" aria-label="pagination">
            <a class="pagination-previous">Previous</a>
            <a class="pagination-next">Next page</a>
            <ul class="pagination-list">
                <li>
                    <a class="pagination-link" aria-label="Goto page 1">1</a>
                </li>
                <li>
                    <span class="pagination-ellipsis">&hellip;</span>
                </li>
                <li>
                    <a class="pagination-link" aria-label="Goto page 45">45</a>
                </li>
                <li>
                    <a class="pagination-link is-current" aria-label="Page 46" aria-current="page">46</a>
                </li>
                <li>
                    <a class="pagination-link" aria-label="Goto page 47">47</a>
                </li>
                <li>
                    <span class="pagination-ellipsis">&hellip;</span>
                </li>
                <li>
                    <a class="pagination-link" aria-label="Goto page 86">86</a>
                </li>
            </ul>
        </nav>
    </div>
</template>