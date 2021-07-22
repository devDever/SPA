<template>
  <b-row class="create">
    <b-col lg="12">
      <h1>Create</h1>
    </b-col>
    <b-col lg="6">
      <b-form class="d-flex flex-column" @submit.prevent="submitHandler()">
        <b-input
          class="mb-4"
          v-model="title"
          type="text"
          placeholder="Title"
          value=""
          required
        />
        <b-form-tags class="mb-4" v-model="tags" />
        <div class="textarea d-flex flex-column">
          <b-form-textarea
            maxlength="500"
            for="description"
            value=""
            v-model="description"
          />
          <span class="align-self-end">{{ description.length }} / 500</span>
        </div>
        <b-input class="mb-4" value="" type="date" v-model="date" />
        <b-button variant="primary align-self-end" type="submit"
          >Create task</b-button
        >
      </b-form>
    </b-col>
  </b-row>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data: () => ({
    title: "Hello",
    description: "",
    tags: [],
    date: "",
  }),
  methods: {
    submitHandler() {
      const task = {
        title: this.title,
        description: this.description,
        id: Date.now(),
        status: "active",
        tags: this.tags,
        date: this.date,
      };
      this.$store.dispatch("createTask", task);
      this.$router.push("/list");
    },
  },
  components: {},
};
</script>
