<template>
  <div>
    <header>
      <Navtop />
     </header>
    <main>
      <slot></slot>
    </main>
    
      <Footer />

  </div>
</template>


<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

// initialize components based on data attribute selectors
onMounted(() => {
    initFlowbite();
})
</script>


<style>
</style>