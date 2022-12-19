<template>
  <div class="container p-5">
    <h1>Find your best Store</h1>
    <div class="row">
      <div v-for="data in data" :key="data.id" class="col-sm-4">
        <div class="card text-bg-dark m-5" style="width: 25rem;">
          <span>
            <img v-for="image in data.metadata" :key="image.index" :src="image" class="card-img-top" alt="..."
              style="height:350px">
          </span>
          <div class="card-body">
            <h5 class="card-title">{{ data.name }}</h5>
            <p class="">{{ data.description }}</p>
            <a :href="'https://paystack.com/pay/' + data.slug" class="btn btn-primary">Visit Store</a>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      data: [],
    };
  },
  computed() {
    data = this.listProduct();
  },
  mounted() {
    this.listProduct();
  },
  methods: {
    async listProduct() {
      try {
        const config = {
          headers: {
            Authorization:
              "Bearer sk_test_be442dc19bf2d7002b19cd3d8e03486959523281",
            "content-type": "application/json",
          },
        };
        const response = await axios.get(
          "https://api.paystack.co/page",
          config
        );
        console.log(response);
        this.data = response.data.data;
        return response;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style>

</style>