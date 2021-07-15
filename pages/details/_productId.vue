<template>
  <section id="product-detail">
    <component :is="'ProductCard'" :product="product" />
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
    return { product }
  },
  head() {
    const { name } = this.product
    const metaDescription = `Lagi Sale! Beli ${name} di Nuxt Store. Dapatkan Harga Terbaik dan Dijamin Original!`
    return {
      title: `Lagi Sale! | Beli ${name} di Nuxt Store`,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: metaDescription,
        },
      ],
    }
  },
}
</script>
