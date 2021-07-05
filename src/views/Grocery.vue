<template>
  <div class="list-wrap">
    <div class="item-wrap" :class="{'item-added': item.isCarted}" v-for="item in groceryItems" :key="item" @click="toggleItemCarted(item)">
      <div class="item">
        <div>{{ item.name }}</div>
        <div>${{ item.price }}</div>
      </div>
    </div>
  </div>
  <div class="cart" v-if="totalCartCost">
    <div class="item-wrap" v-for="item in groceryItems" :key="item">
      <div class="item" v-if="item.isCarted">
        <div>{{ item.name }} &nbsp; @ &nbsp; {{ item.quantity }} x ${{ item.price }}</div>
        <div>${{ item.price * item.quantity }}</div>
        <div class="controls">
          <div @click="item.quantity ? item.quantity-- : toggleItemCarted(item)">-</div>
          <div @click="item.quantity++">+</div>
          <div @click="toggleItemCarted(item)">x</div>
        </div>
      </div>
    </div>
    <div class="total-wrap" v-if="totalCartCost">
      <div>Total</div>
      <div>${{ totalCartCost }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      groceryItems: [
        {name: 'Milk', isCarted: false, price: 10, quantity: 0},
        {name: 'Fish', isCarted: false, price: 20, quantity: 0},
        {name: 'Lettuce', isCarted: false, price: 5, quantity: 0},
        {name: 'Rice', isCarted: false, price: 2.5, quantity: 0},
      ],
    }
  },
  computed:{
      totalCartCost(){
        let total = 0
        for (const item of this.groceryItems){
            total+=item.price * item.quantity
        }
        return total
    }
  },
  methods: {
    toggleItemCarted(item) {
      item.isCarted = !item.isCarted
      item.isCarted ? item.quantity++ : (item.quantity = 0)
    }
  },
}
</script>

<style lang="scss" scoped>
div {
  @import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;700;900&display=swap');
  font-family: Source Sans Pro;
  font-size: 1.2rem;
}

.list-wrap {
  display: inline-flex;
  flex-direction: column;

  .item-wrap {
    display: flex;
    background-color: #ddd;
    padding: 1rem;
    min-width: 16rem;
    margin: 0.5rem;
    border-radius: 0.75rem;
    cursor: pointer;

    .item {
      display: flex;
      flex: 1;
      justify-content: space-between;
    }
  }

  .item-added {
    opacity: 0.5;
  }
}

.cart {
  position: absolute;
  top: 0;
  right: 0;
  min-width: 24rem;
  padding: 1rem;
  background-color: #444;
  color: white;

  .item-wrap {
    margin: 0.5rem;

    .item {
      display: flex;
      justify-content: space-between;
      background-color: #333;
      padding: 1rem;

      .controls {
        display: none;

        div {
          background-color: orange;
          color: #111;
          width: 2rem;
          margin: 0 0.2rem;
          border-radius: 0.25rem;
          display: flex;
          justify-content: center;
          align-items: center;
          cursor: pointer;
        }
      }

      &:hover {
        .controls {
          display: flex;
        }
      }
    }
  }
  .total-wrap {
      background-color: orange;
      margin: 0.5rem;
      padding: 1rem;
      color: #111;
      display: flex;
      justify-content: space-between;
  }
}
</style>
