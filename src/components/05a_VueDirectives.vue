<template>
  <!--
    VueDirectives
    demo_01-05: Basic Directives (v-text, v-once, v-html, v-bind, v-if, v-show)
   -->
  <div>
    <h1 v-show="true" v-text="mytext">Loading...</h1>
    <h2 v-show="true" v-html="myhtml" />
    <a
      :href="link.url"
      :target="link.target"
      :tabindex="link.tabindex"
      v-text="link.title"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      // v-text
      mytext: 'Einkaufsliste von Kimo & Fabio',
      // v-html
      myhtml: 'Hallo, unten findest du die Einkaufsliste',
      // v-bind
      link: {
        url: 'http://localhost:8080/about',
        target: '_blank',
        tabindex: '0',
        title: 'Zur Einkaufsliste'
      },
    }
  },
}
</script>

<style lang="scss" scoped>
h2 {
  margin: 50px 0 0 10px;
  font-weight: normal;
}
a {
  display: block;
  color: #A163E6;
}



</style>
