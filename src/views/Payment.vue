<template>
  <div class="container">
    <h1>Payment</h1>
    <form class="text-bg-dark p-4 rounded" @submit.prevent="createProduct()">
      <div class="form-group">
        <label for="name">Email</label>
        <input type="email" class="form-control" id="name" placeholder="Email Address" v-model="email" required />
      </div>
      <div class="form-group">
        <label for="description">Amount</label>
        <input class="form-control" type="number" placeholder="$ Amount" v-model="amount">
      </div>
      <div class="form-group">
        <input class="form-control mt-3 btn btn-success" type="submit" value="Pay">
      </div>
    </form>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>