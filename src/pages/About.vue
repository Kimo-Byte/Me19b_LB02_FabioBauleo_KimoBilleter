<template>
  <div class="about">
    <h1>Einkaufsliste {{$route.params.user}}</h1>

    <MyShoppinglist/>

  </div>
</template>

<script>
import Shoppinglist from "./../components/11_ShoppingList"

export default {
  name: 'app',
  components: {
    MyShoppinglist: Shoppinglist

  }
}
</script>

<style lang="scss">
//Import of global-style
@import '../styles/global';
</style>