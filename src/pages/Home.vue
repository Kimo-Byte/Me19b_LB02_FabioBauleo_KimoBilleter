<template>
  <div>

    <MyVueDirectives/>

  </div>
</template>

<script>
import VueDirective from "./../components/05a_VueDirectives"

export default {
  name: 'app',
  components: {
    MyVueDirectives: VueDirective

  }
}
</script>

