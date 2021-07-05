<template>
  <div class="view-wrap">
    <div class="grocery-list">
      <div class="item" v-for="item in groceryList" :key="item" @click="addToCart(item)" :class="{selected: item.isSelected === true}">
        <div>{{ item.product }}</div>
        <div>${{ item.amount }}</div>
      </div>
    </div>
    <div class="cart">
      <div class="item" v-for="item in groceryList" :key="item">
        <div class="item-wrap" v-if="item.isSelected === true">
          <div>{{ item.product }}</div>
          <div>@ &nbsp; {{ item.quantity }} x ${{ item.amount }}</div>
          <div>${{ item.quantity * item.amount }}</div>
          <div class="control-wrap">
            <div @click="updateItemQty('minus', item)">-</div>
            <div @click="updateItemQty('plus', item)">+</div>
            <div @click="removeItem(item)">x</div>
          </div>
        </div>
      </div>
      <div class="total" v-if="calculateTotal > 0">
        <div>Total</div>
        <div>${{ calculateTotal }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    // global data (this!!!!)
    return {
      isMarried: true,
      groceryList: [
        {product: 'Tomato', amount: 10, isSelected: false, quantity: 0},
        {product: 'Milk', amount: 50, isSelected: false, quantity: 0},
        {product: 'Fish', amount: 75, isSelected: false, quantity: 0},
        {product: 'Bread', amount: 25, isSelected: false, quantity: 0},
      ],
    }
  },
  computed:{
      calculateTotal() {
      // loop1 container = 10
      // loop2 container = 40
      // loop3 container = 80
      // loop4 container = 85

      let total = 0
      for (const item of this.groceryList) {
        // 10, 30, 40, 5
        total = total + item.amount * item.quantity
      } // hint
      console.log('calculateTotal was used')
      return total
    },
  },
  methods: {
    addToCart(item) {
      item.isSelected = !item.isSelected

      if (item.isSelected === true) {
        item.quantity++
      } else {
        item.quantity = 0
      }
    },
    updateItemQty(mode, item) {
      // mode => "plus" or "minus"
      if (mode === 'plus') {
        item.quantity++
      } else {
        if (item.quantity > 0) {
          item.quantity--
        } else {
          item.isSelected = false
        }
        // if our qty > 0 then we subtract, if our qty is 0 then we change isSelected to false
      }
    },
    removeItem(item) {
      item.isSelected = false
      item.quantity = 0
    },
    toggleMarried() {
      this.isMarried = !this.isMarried
    },
  },
}
</script>

<style lang="scss" scoped>
div {
  font-size: 1.5rem;
}

.view-wrap {
  display: flex;
  justify-content: space-between;

  .grocery-list {
    .item {
      display: flex;
      justify-content: space-between;
      background-color: #ddd;
      padding: 1rem;
      border-radius: 0.5rem;
      cursor: pointer;
      width: 14rem;
      margin: 0.5rem;
    }

    .selected {
      background-color: #e8e8e8;
      color: #888;
    }
  }

  .cart {
    .item {
      display: flex;
      width: 30rem;

      .item-wrap {
        flex: 1;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem;
        background-color: #ddd;
        border-radius: 0.5rem;
        margin: 0.25rem;
        height: 3rem;

        .control-wrap {
          display: none;
          // justify-content: space-between;
          // background-color: orange;

          div {
            background-color: orange;
            margin: 0 0.5rem;
            padding: 0.25rem 1rem;
            border-radius: 0.25rem;
            cursor: pointer;
          }
        }

        &:hover {
          .control-wrap {
            display: flex;
          }
        }
      }
    }

    .total {
      display: flex;
      justify-content: space-between;
      background-color: orange;
      padding: 1rem;
      border-radius: 0.5rem;
      margin: 0.25rem;
    }
  }
}
</style>
