<template>
  <div>
    <div id="app">
    </div>
<Nav />
    <MyComponent/>

  </div>
</template>

<script>
/* Import all components */

import SimpleNav from "./components/SimpleNav"
import Nav from "./components/Nav"



export default {
  name: 'app',
  components:{
    MyComponent: SimpleNav,
    Nav: Nav,




  }
}
</script>

<style lang="scss">
//Import of global-style
@import "styles/global";
</style>
