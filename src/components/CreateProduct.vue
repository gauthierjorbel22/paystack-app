<template>
  <div class="container">
    <form>
      <div class="form-group">
        <label for="name">Name</label>
        <input
          type="text"
          class="form-control"
          id="name"
          placeholder="Product Name"
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
        ></textarea>
      </div>
      <div class="form-group">
        <label for="price">Price</label>
        <input
          type="number"
          class="form-control"
          id="price"
          placeholder="Product Price"
        />
      </div>
      <div class="form-group">
        <label for="currency">Currency</label>
        <select class="form-control" name="currency" id="currency">
          <option>Rand</option>
          <option>Naira</option>
          <option>Ghana</option>
        </select>
      </div>
      <div class="form-group">
        <label for="unlimited">Unlimited</label>
        <select class="form-control" name="unlimited" id="unlimited">
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
        />
      </div>
      <div class="form-group pt-3">
        <input
          type="submit"
          class="form-control btn btn-success"
          value="submit"
        />
      </div>
    </form>
  </div>
</template>

<script setup>
</script>

<style>
</style>