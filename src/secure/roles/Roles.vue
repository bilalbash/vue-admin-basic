<template>
  <div class="table-responsive">
    <table class="table table-striped table-sm">
      <thead>
        <tr>
          <th>#</th>
          <th>Name</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="role in roles" :key="role.id">
          <td>{{ role.id }}</td>
          <td>{{ role.name }}</td>
          <td>
            <div class="btn-group mr-2">
              <router-link
                :to="`/roles/${role.id}/edit`"
                class="btn btn-sm btn-outline-secondary">
                Edit
              </router-link>
              <a
                href="javascript:void(0)"
                class="btn btn-sm btn-outline-secondary"
                @click="delRole(role.id)">
                Delete
              </a>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="ts">
import axios from "axios";
import { ref, onMounted } from "vue";
import { Entity } from "@/interfaces/entity";

export default {
  name: "Roles",
  setup() {
    const roles = ref([]);

    onMounted(async () => {
      const response = await axios.get("roles");
      roles.value = response.data.data;
    });

    const delRole = async (id: number) => {
      if (confirm("r u sure?")) {
        await axios.delete(`roles/${id}`);
        roles.value = roles.value.filter((e: Entity) => e.id !== id);
      }
    };

    return {
      roles,
      delRole,
    };
  },
};
</script>

<style scoped></style>
