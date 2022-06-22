<template>
  <div class="container">
    <div class="user-input">
      <input
          placeholder="Füge Produkte mit Enter hinzu"
          v-model="input"
          @keyup.enter="addItem"
          ref="input"
      /><button @click="addItem">Zur Liste hinzufügen</button>
    </div>

    <ul v-if="shoppingList">
      <li v-for="item in shoppingList" :key="item" class="item"
      ><span>{{ item }}</span>
        <button class="button-remove" @click="deleteItem(item)">Entfernen</button>
      </li>
    </ul>
    <!-- Version 2
    <ul v-if="shoppingList">
      <li v-for="(item,index) in shoppingList" :key="index" class="item"
      ><span>{{ item }}</span>
        <button class="button--remove" @click="deleteItem(index)">Remove</button>
      </li>
    </ul>
    -->
    <br />
    <button class="button-delete" @click="deleteItem()">Liste löschen</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: '',
      shoppingList: [],
    }
  },
  methods: {
    addItem() {
      // Don't allow adding to the list if empty
      if (!this.input) return
      this.shoppingList.push(this.input)
      // Clear the input after adding
      this.input = ''
      // Focus the input element again for quick typing!
      this.$refs.input.focus()
    },
    deleteItem(item) {
      //only for info purposes
      let index = this.shoppingList.indexOf(item);
      console.log(`item: ${item} at index: ${index}`);
      //no parameter provided ..
      if (item == null){
        //.. deleteAll has been pressed
        this.shoppingList = [];
      } else {
        //assign filtered shopping list without deleted item
        this.shoppingList = this.shoppingList.filter(el => el !== item);
      }
    },
    deleteItem_v2(i) {
      if (i == null) {
        this.shoppingList = []
      } else {
        this.shoppingList = this.shoppingList.filter((item,el) => el !== i);
      }
      //Verkürzte Variante von deleteItem(i)
      // this.shoppingList = i
      //     ? this.shoppingList.filter((item, x) => x !== i)
      //     : []
    },
  },
}
</script>

<style lang="scss">


.container {
  max-width: 550px;
  margin-top: 50px;
}

.item {
  display: flex;
  justify-content: space-between;
}

// Type
.h2 {
  font-size: 20px;
}

.user-input {
  display: flex;
  align-items: center;
  padding-bottom: 20px;
  width: 520px;

  input {
    width: 300px;
    padding: 10px 6px;
    margin-right: 14px;
  }
}

.item {
  display: flex;
  align-items: center;
}

// Buttons
button {
  padding: 12px;
  font-weight: bold;
  border: none;
  color: white;
  background: #A163E6;

}

.button-delete {
  margin: 0 auto;
  background:#A163E6;
  float: right;
  width: 520px;
}

.button-remove {
  background: none;
  color: #A163E6;
  text-transform: uppercase;
  font-size: 11px;
  align-self: flex-end;
}

ul {
  display: block;
  margin: 0 auto;
  padding: 40px;
  border: 5px solid rgba(161, 99, 230);


}
</style>
