<template>
  <div
    class="description"
    :class="{ show: active.drawer }"    
  >
    <div class="description__wrapper">
      <button
        class="description__button description__button--close"
        type="button"
        @click="$emit('close')"
      >
        Close
      </button>
      <div v-if="product" class="description__content">
        <h3 class="description__title text-center">{{ product.name }}</h3>
        <p class="description__description">{{ product.description }}</p>
        <h3 class="description__price text-center">
          Price:${{ product.price }}
        </h3>

        <div class="description__total">
          <h3 class="description__cart">In Cart</h3>
          <h4 class="description__total">{{}}</h4>
        </div>
        <div class="description__inner">
          <button
            class="description__button description__button--remove"
            type="button"
          >
            Remove
          </button>
          <button
            class="description__button description__button--add"
            type="button"
          >
            Add
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductDescription',
  props: ['product', 'active'],
  emits: ['close'],
};
</script>

<style lang="scss" scoped>
.description {
  width: 100%;
  height: 100%;
  position: fixed;
  left: 0;
  top: 0;
  z-index: 100;
  display: none;

  &.show {
    display: block;
  }
  &__wrapper {
    height: 100vh;
    background-color: #fff;
    padding: 15px;
    z-index: 110;
    overflow-y: scroll;
    
  }
  &__content {
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
  &__button {
    width: 150px;
    border: none;
    padding: 10px;
    border-radius: 5px;
    margin: 0 5px 50px 5px;
    cursor: pointer;
    color: #fff;
    &:hover {
      transition: all 0.5s ease-in;
    }
  }

  &__button--close {
    background-color: indigo;
    &:hover {
      background-color: rgb(120, 57, 165);
    }
  }

  &__content {
  }

  &__title {
  }

  &__description {
    padding: 20px;
    line-height: 1.5rem;
  }

  &__price {
  }

  &__total {
  }

  &__cart {
  }

  &__inner {
  }

  &__button--remove {
    background-color: rgb(221, 33, 33);
    &:hover {
      background-color: rgb(196, 62, 62);
    }
  }

  &__button--add {
    background-color: forestgreen;
    &:hover {
      background-color: rgb(79, 141, 79);
    }
  }
}
.show {
  display: block;
}
</style>
