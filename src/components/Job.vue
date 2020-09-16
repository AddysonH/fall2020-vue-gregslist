<template>
  <div class="col-4">
    <div class="card">
      <div class="card-body">
        <h4 class="card-title">{{jobData.company}} - {{jobData.hours}}</h4>
        <p class="card-text">{{jobData.description}}</p>
        <div class="d-flex justify-content-between">
          <button
            class="btn btn-outline-danger"
            onclick="app.housesController.removeHouse('${this.id}')"
          >Delete</button>
          <button
            class="btn btn-outline-info"
            onclick="app.housesController.bid('${this.id}')"
          >+ $100</button>
          <p>{{jobData.rate}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Job",
  props: {
    jobData: {
      type: Object,
      required: true,
    },
  },
};
</script>