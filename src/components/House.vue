<template>
  <div class="col-4">
    <div class="card">
      <img class="card-img-top" src="${this.imgUrl}" alt />
      <div class="card-body">
        <h2 class="card-title"></h2>
        <h3>Bedrooms: {{houseData.bedrooms}}</h3>
        <h3>Bathrooms: {{houseData.bathrooms}}</h3>
        <h3>Levels: {{houseData.levels}}</h3>
        <p class="card-text">{{houseData.description}}</p>
        <div class="d-flex justify-content-between">
          <button
            class="btn btn-outline-danger"
            onclick="app.housesController.removeHouse('${this.id}')"
          >Delete</button>
          <button
            class="btn btn-outline-info"
            onclick="app.housesController.bid('${this.id}')"
          >+ $100</button>
          <p>{{houseData.price}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Houses",
  props: {
    houseData: {
      type: Object,
      required: true,
    },
  },
};
</script>