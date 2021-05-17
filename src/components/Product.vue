<template>
  <div>
    <main>
      <div class="featured-pack">
        <h1>{{ currentItem.name }} - €{{ currentItem.price }}</h1>
      </div>
      <div class="wrap-prod">
        <div class="prod-left">
          <img :src="currentItem.image" />
          <div class="prod-right">
            <h2>Popis</h2>
            <p>
              {{ currentItem.description }}
            </p>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cart: [],
      currentItem: this.$route.params,
      avaibleProducts: [],
      computed: {
        showProduct() {
          const id = this.$route.params.id;
          const product = this.avaibleProducts.find((p) => p.uuid == id);
          return product;
        },
      },
    };
  },
};
</script>

<style></style>
