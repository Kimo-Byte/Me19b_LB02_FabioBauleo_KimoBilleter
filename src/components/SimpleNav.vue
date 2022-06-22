<template>
  <div class="container">
    <div class="user-input">
      <button class="button--navi" @click="nachHause()">nach Hause</button>
      <button class="button--navi" @click="zurueck()">Zurück</button>
      <button class="button--navi" @click="nachVorne()">Nach Vorne</button>
    </div>
  </div>
</template>


<script>
export default {
  methods: {
    nachHause() {
      this.$router.push('/home');
    },
    zurueck() {
      this.$router.go(-1);
    }, nachVorne() {
      this.$router.go(1);
    }
  }
}
</script>

<style lang="scss">

.container {
  max-width: 600px;
  margin: 80px auto;
}


.user-input {
  display: flex;
  align-items: center;
  padding-bottom: 20px;

  input {
    width: 100%;
    padding: 10px 6px;
    margin-right: 10px;
  }
}

// Buttons
button {
  padding: 10px;
  font-weight: bold;
  border: none;
  color: white;

}

.button--navi {
  margin: 1px auto;
  background: #A163E6;
}

</style>
