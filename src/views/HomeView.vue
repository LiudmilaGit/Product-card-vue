<template>
  <div class="home">
    <div class="home__container">
      <ProductCard 
      v-for="(item,id) in items"
      :key="item.id"
      :product ="item"
      v-on:view-product = "viewProduct($event)"
      />
    </div>
  </div>
</template>

<script>
import products from '@/data/products';
import ProductCard from '@/components/Products/ProductCard.vue';
export default {
  name: 'HomeView',
  components: {ProductCard},
  data() {
    return {
      items: products,
    };
  },
  methods: {
    viewProduct(product){
      this.product = product
      console.log(this.product)
    }
  },
};
</script>
<style lang="scss" scoped>
.home {
  &__container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>
