<template>
  <div class="home">
    <ProductDescription
      :product="product"
      :active="active"
      v-on:close="close()"
    />
    <div class="home__cards-container">
      <ProductCard
        v-for="(item, id) in items"
        :key="item.id"
        :product="item"
        v-on:view-product="viewProduct($event)"
      />
    </div>
  </div>
</template>

<script>
import products from '@/data/products';
import ProductCard from '@/components/Products/ProductCard.vue';
import ProductDescription from '@/components/Products/ProductDescription.vue';
export default {
  name: 'HomeView',
  components: { ProductCard, ProductDescription },
  data() {
    return {
      items: products,
      product: null,
      active: {
        drawer: false,
      },
    };
  },
  methods: {
    viewProduct(product) {
      this.product = product;
      this.active.drawer = true;
    },
    close() {
      this.active.drawer = false;
    },
  },
};
</script>
<style lang="scss" scoped>
.home {
  display: flex;
  &__cards-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    max-width: 1200px;
    margin: 0 auto;
    gap: 20px;
  }
}
</style>
