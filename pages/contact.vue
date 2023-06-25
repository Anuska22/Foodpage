<template>
    <div>
        <div class="container  py-4">
          <div class="loading" v-if="pending">
        <img src="~/assets/images/loading.gif"  alt="">
      </div>
    <h1 class=" text-lg">Contact Us</h1>
    <form>
      <div class="form-group py-4">
        <label for="name">Name:</label>
        <input type="text" id="name" placeholder="Enter your name">
      </div>
      <div class="form-group">
        <label for="email">Email:</label>
        <input type="text" id="email" placeholder="Enter your email address">
      </div>
      <div class="form-group">
        <label for="message">Message:-</label>
        <textarea id="message" placeholder="Enter your message"></textarea>
      </div>
      <button  class="border text-white bg-blue-500 rounded px-5 " type="submit">Submit</button>
    </form>
    <div class="message">
      <!-- Success message will be displayed here -->
    </div>
  </div>
    </div>
</template>

<script setup>

</script>

<style >

</style>