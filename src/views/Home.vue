<template>
  <div class="home" style="min-height: 80vh">
    <HelloWorld msg="Welcome to E-Shop-E"/>
    <div class="row d-flex justify-content-center">
      <!-- content card  -->
      <ProductCards
        v-for="product in products"
        :key="product.id"
        :product="product"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import ProductCards from '../components/ProductCards'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    ProductCards
  },
  created () {
    this.$store.dispatch('changePage', 'home')
    this.$store.dispatch('fetchProducts')
  },
  computed: {
    products () {
      return this.$store.state.products
    }
  }
}
</script>
