<template>
  <div class="row my-3">
    <div class="col" id="form">
      <form onsubmit="app.carsController.createHouse()" class="form-inline">
        <div class="form-group p-1">
          <label class="mr-1" for="bedrooms">Bedrooms</label>
          <input
            type="text"
            name="bedrooms"
            id="bedrooms"
            class="form-control"
            placeholder="Bedrooms..."
          />
        </div>
        <div class="form-group p-1">
          <label class="mr-1" for="Bathrooms">Bathrooms</label>
          <input
            type="text"
            name="Bathrooms"
            id="Bathrooms"
            class="form-control"
            placeholder="Bathrooms..."
          />
        </div>
        <div class="form-group p-1">
          <label class="mr-1" for="levels">Levels</label>
          <input
            type="number"
            name="levels"
            id="levels"
            class="form-control"
            placeholder="levels..."
            min="1900"
            max="3"
          />
        </div>
        <div class="form-group p-1">
          <label class="mr-1" for="price">Price</label>
          <input type="number" name="price" id="price" class="form-control" placeholder="Price..." />
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
        <div class="form-group p-1">
          <label class="mr-1" for="img">Image Url</label>
          <input type="url" name="img" id="img" class="form-control" placeholder="Image Url..." />
        </div>
        <button type="submit" class="btn btn-outline-success">Add House</button>
      </form>
    </div>
    <div>
      <house v-for="house in houses" :key="house._id" :houseData="house" />
    </div>
  </div>
</template>

<script>
import House from "../components/House.vue";
export default {
  name: "Houses",
  mounted() {
    this.$store.dispatch("getAllHouses");
  },
  computed: {
    houses() {
      return this.$store.state.houses;
    },
  },
  components: {
    House,
  },
};
</script>