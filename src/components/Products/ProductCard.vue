<template>
  <div class="card">
    <h3 class="card__title">{{ product.name }}</h3>
    <p class="card__muted">{{ product.category }}</p>
    <h5 class="card__price">Price: ${{ product.price }}</h5>
    <p class="card__description">
      <strong>Description:</strong> {{ description }}
    </p>
    <button
      @click.prevent="$emit('view-product', product)"
      class="card__button"
    >
      View Product
    </button>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: ['product'],
  computed: {
    description() {
      return this.product.description.substring(0, 150);
    },
  },
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 80%;  
  padding: 10px;
  border-radius: 10px;
  background-color: rgb(245, 244, 244);
  box-shadow: 0 0 5px grey;
  color: #000;
  @media (min-width: 500px) {
    width: 350px;
  }

  &__title {
    font-size: 24px;
  }
  &__price {
    font-size: 18px;
  }

  &__description {
    color: grey;
  }

  &__muted {
  }

  &__button {
    padding: 10px;
    background-color: #543e92;
    border: none;
    color: #fff;
    font-weight: bold;
    font-size: 14px;
    border-radius: 5px;
    cursor: pointer;
    &:hover {
      background-color: #6e54a0;
      transition: all 0.3s ease-in;
    }
  }
}
</style>
