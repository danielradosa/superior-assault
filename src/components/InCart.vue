<template>
  <div>
    <main>
      <div class="wrap">
        <div class="contact">
          <h2>
            MÁŠ <span>{{ countOfCartProducts }}</span> 
            <span class="obyc" v-if="countOfCartProducts === 1"> VEC </span> 
            <span class="obyc" v-else-if="countOfCartProducts >= 2 && countOfCartProducts <= 4"> VECI </span> 
            <span class="obyc" v-else> VECÍ </span> V
            <span>KOŠÍČKU</span>
          </h2>
        </div>
      </div>
    </main>

    <div class="cart">
      <div class="item" v-for="(item, index) in myCart" v-bind:key="index">
        <div class="left-item">
          <img :key="item.image" :src="item.image" />
        </div>
        <div class="right">
          <h2>
            {{ item.name
            }} <span class="remove" v-on:click="removeFromCart">X</span>
          </h2>
          <h3>
            Price <span>€{{ item.price }}</span>
          </h3>
        </div>
      </div>
      <div class="total">
        <h3>Totálna Cena: <span>€{{ getTotal }}</span></h3>
      </div>
      <div class="pay-btn">
        <button>ZAPLAŤ</button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import { mapMutations } from "vuex";

export default {
  methods: {
    ...mapMutations(["REMOVE_FROM_CART"]),
    removeFromCart(item) {
      this.REMOVE_FROM_CART(item);
    },
  },
  computed: {
    ...mapGetters(["countOfCartProducts"]),
    ...mapGetters(["myCart"]),
    ...mapGetters(["getTotal"]),
  },
  props: ["product"],
  data() {
    return {
      cart: [],
      currentItem: this.$route.params,
    };
  },
};
</script>

<style>
.obyc {
  color: #20ffe2;
  text-decoration: none;
}
</style>
