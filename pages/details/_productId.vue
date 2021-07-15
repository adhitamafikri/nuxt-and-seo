<template>
  <section id="product-detail">
    <component :is="'ProductCard'" v-if="product" :product="product" />
  </section>
</template>

<script>
import { getProduct as apiGetProduct } from '@/services/api'

export default {
  name: 'ProductDetailsPage',
  components: {
    ProductCard: () =>
      import(/* product-card */ '@/components/ProductCard.vue'),
  },
  async asyncData({ params }) {
    const { productId } = params
    const product = await apiGetProduct(productId)
    console.dir('PODUCT', product)
    return { product }
  },
}
</script>
