<template>
  <div>
    <h2>Zur Kasse</h2>
    Dein Rabatt beträgt CHF {{ tot = (cartTotal / 100 * rabatt).toFixed(2) }}, Total: {{cartTotal - tot}} CHF
    <b-button variant="primary" v-show="cartTotal > 0" @click="checkout">Checkout</b-button>
  </div>
</template>

<script>
import {mapGetters} from 'vuex';
import watchers from './01_Watchers';

export default {

  name: 'Cart',
  computed: mapGetters(['cartTotal']),
  methods: {
    checkout() {
      alert('Checkout erfolgreich!');
    }
  },
    data() {
      return {
          tot: 0,
          rabatt: watchers.data().discounts,


      }


}
}

</script>

