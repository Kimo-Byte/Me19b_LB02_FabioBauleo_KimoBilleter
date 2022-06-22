<!--
  Using Watchers to Set New Values
-->
<template>
  <div class="rabattcontainer">
    <h1>Rabatt</h1>
    <div>
      Sommer SALE!
      <strike v-show="oldDiscount">war {{ oldDiscount }}%</strike><br/>
      <strong> Jetzt {{ discount }}% billiger </strong><br/><br/>
      <a @click="updateDiscount">Erhöhe den Rabatt um 5%</a>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      oldDiscount: 0,
      discounts: 35,
      discount: 0
    }
  },
  watch: {
    discount: {

      handler: function (newVal, oldVal){
        console.log(`Neuer Discount:(${newVal}%) / Alter Discount: (${oldVal}%).`);
        this.oldDiscount = oldVal;
      },
      immediate: false,
      deep: true
    }

  },
  methods: {
    updateDiscount(){
      if(this.discount < 50){
      this.discount = this.discount + 5;}
      else{
        this.discount = 50;
      }
    }
  }
}
</script>
<style lang="scss" scoped>

.rabattcontainer {
  margin: 30px;
}

.rabattcontainer a {
  background: #A163E6;
  font-size: 15px;
  color: white;
  padding: 10px 20px;
}
</style>
