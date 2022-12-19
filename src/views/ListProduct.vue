<template>
  <div class="container">
    <div>
      <div class="" v-for="data in data" :key="data.id">
        <div class="card text-bg-light p-5 m-5">
          <h2>{{ data.name }}</h2>
          <p>Product ID: {{ data.id }}</p>
          <p>{{ data.description }}</p>
          <p>Product Code: {{ data.product_code }}</p>
          <p>Price: {{ data.currency }} {{ data.price }}</p>
          <p>Quantity: {{ data.quantity }}</p>
          <div class="row">
            <div v-for="img in data.files" :key="img" class="col-lg-4 col-md-12 mb-4 mb-lg-0">
              <img :src="img.path" alt="" class="" style="width:200px; height: 200px" />
            </div>
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
          "https://api.paystack.co/product",
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