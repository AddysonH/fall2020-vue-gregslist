<template>
  <div>
    <form onsubmit="app.carsController.createJob()" class="form-inline">
      <div class="form-group p-1">
        <label class="mr-1" for="Company">Company</label>
        <input
          type="text"
          name="Company"
          id="Company"
          class="form-control"
          placeholder="Company..."
        />
      </div>
      <div class="form-group p-1">
        <label class="mr-1" for="hours">hours</label>
        <input type="text" name="hours" id="hours" class="form-control" placeholder="hours..." />
      </div>
      <div class="form-group p-1">
        <label class="mr-1" for="rate">rate</label>
        <input type="number" name="rate" id="rate" class="form-control" placeholder="rate..." />
      </div>
      <div class="form-group p-1">
        <label class="mr-1" for="description">Description</label>
        <input
          type="text"
          name="description"
          id="description"
          class="form-control"
          placeholder="Description..."
        />
      </div>
      <button type="submit" class="btn btn-outline-success">Add Job</button>
    </form>
    <div>
      <job v-for="job in jobs" :key="job._id" :jobData="job" />
    </div>
  </div>
</template>

<script>
import Job from "../components/Job.vue";
export default {
  name: "Jobs",
  mounted() {
    this.$store.dispatch("getAllJobs");
  },
  computed: {
    jobs() {
      return this.$store.state.jobs;
    },
  },
  components: {
    Job,
  },
};
</script>