<template>
  <div class="container">
    <div>
      <div v-for="data in data" :key="data.id">
        <div class="card">
          <p>{{ data.id }}</p>
          <p>{{ data.name }}</p>
          <p>{{ data.description }}</p>
          <p>{{ data.product_code }}</p>
          <p>{{ data.currency }}</p>
          <p>{{ data.price }}</p>
          <p>{{ data.quantity }}</p>
          <p v-for="img in data.files" :key="img">
            <img :src="img.path" alt="" class="w-50" />
          </p>
        </div>
      </div>

      <!-- {{ data }} -->
      <input
        type="submit"
        class="btn btn-success"
        value="Click"
        @click="listProduct()"
      />
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