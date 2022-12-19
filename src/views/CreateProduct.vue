<template>
    <div class="container mt-5">
      <h1>Create Product</h1>
      <form class="text-bg-dark p-4 mt-5 rounded" @submit.prevent="createProduct()">
        <div class="form-group">
          <label for="name">Name</label>
          <input
            type="text"
            class="form-control"
            id="name"
            placeholder="Product Name"
            v-model="name"
            required
          />
        </div>
        <div class="form-group">
          <label for="description">Description</label>
          <textarea
            class="form-control"
            name="description"
            id=""
            cols="30"
            rows="3"
            placeholder="Product description"
            v-model="description"
            required
          ></textarea>
        </div>
        <div class="form-group">
          <label for="price">Price</label>
          <input
            type="number"
            class="form-control"
            id="price"
            placeholder="Product Price"
            v-model="price"
            required
          />
        </div>
        <div class="form-group">
          <label for="currency">Currency</label>
          <select
            class="form-control"
            name="currency"
            id="currency"
            v-model="currency"
            required
          >
            <option>ZAR</option>
            <option>NGN</option>
            <option>GHS</option>
            <option>USD</option>
          </select>
        </div>
        <div class="form-group">
          <label for="unlimited">Unlimited</label>
          <select
            class="form-control"
            name="unlimited"
            id="unlimited"
            v-model="unlimited"
            required
          >
            <option>false</option>
            <option>true</option>
          </select>
        </div>
        <div class="form-group">
          <label for="quantity">Quantity</label>
          <input
            class="form-control"
            type="number"
            placeholder="Product Quantity"
            v-model="quantity"
            required
          />
        </div>
        <div class="form-group pt-3">
          <input
            type="submit"
            class="form-control btn btn-success"
            value="Add Product"
          />
        </div>
      </form>
    </div>
  </template>
  
  <script>
  import axios from "axios";
  export default {
    data() {
      return {
        name: null,
        description: null,
        price: null,
        currency: null,
        unlimited: null,
        quantity: null,
      };
    },
    methods: {
      async createProduct() {
        try {
          const config = {
            headers: {
              Authorization:
                "Bearer sk_test_be442dc19bf2d7002b19cd3d8e03486959523281",
              "content-type": "application/json",
            },
          };
          const response = await axios.post(
            "https://api.paystack.co/product",
  
            {
              name: this.name,
              description: this.description,
              price: this.price,
              currency: this.currency,
              unlimited: this.unlimited,
              quantity: this.quantity,
            },
            config
          );
          console.log(response);
          this.$router.push('/list');
          return response;

          

        } catch (error) {
          console.log(error);
        }
      },
    },
  };
  </script>
  
  <style scoped>
  </style>
  