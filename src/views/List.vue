<template>
  <b-row>
    <b-col cols="12">
      <h1>List</h1>
    </b-col>
    <b-col cols="12">
      <table cols="12" v-if="tasks.length" style="width: 100%">
        <thead>
          <tr>
            <th>#</th>
            <th>Title</th>
            <th>Date</th>
            <th>Descrition</th>
            <th>Status</th>
            <th>Open</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(task, idx) in tasks" :key="task.id" class="mb-1">
            <td>{{ idx + 1 }}</td>
            <td>{{ task.title }}</td>
            <td>{{ task.date }}</td>
            <td>
              <div>{{ task.description }}</div>
            </td>
            <td>{{ task.status }}</td>
            <td>
              <router-link
                tag="button"
                class="btn btn-primary"
                :to="/task/ + task.id"
                >Open</router-link
              >
            </td>
          </tr>
        </tbody>
      </table>
      <p v-else>Nothing...</p>
    </b-col>
  </b-row>
</template>

<script>
export default {
  computed: {
    tasks() {
      return this.$store.getters.tasks;
    },
  },
};
</script>
