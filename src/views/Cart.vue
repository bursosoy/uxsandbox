<template>
  <div class="main-wrap">
      <div class="item">
          <div class="quantity">{{ item1.quantity }}</div>
          <div>{{ item1.label }}</div>
          <div class="price">${{ item1.price }}</div>
          <div class="plusminus">
              <div v-if="item1.quantity > 0" @click="updateQuantity('minus',item1)">-</div>
              <div @click="updateQuantity('plus',item1)">+</div>
          </div>
      </div>
      <div class="item">
          <div class="quantity">{{ item2.quantity }}</div>
          <div>{{ item2.label }}</div>
          <div class="price">${{ item2.price }}</div>
          <div class="plusminus">
              <div v-if="item2.quantity > 0" @click="updateQuantity('minus',item2)">-</div>
              <div @click="updateQuantity('plus',item2)">+</div>
          </div>
      </div>
      <div class="item">
          <div class="quantity">{{ item3.quantity }}</div>
          <div>{{ item3.label }}</div>
          <div class="price">${{ item3.price }}</div>
          <div class="plusminus">
              <div v-if="item3.quantity > 0" @click="updateQuantity('minus',item3)">-</div>
              <div @click="updateQuantity('plus',item3)">+</div>
          </div>
      </div>
      <div class="total">
          <div>Total</div>
          <div>${{ getTotal() }}</div>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            item1:{
                label: "Beef Steak",
                isHovered: false,
                price: 10.00,
                quantity: 0,
                bought: 0
            },
            item2:{
                label: "Carrot",
                isHovered: false,
                price: 1.50,
                quantity: 0,
                bought: 0
            },
            item3:{
                label: "French Bread",
                isHovered: false,
                price: 2.50,
                quantity: 0,
                bought: 0
            }
        }
    },
    methods:{
        getTotal(){
            return (this.item1.quantity * this.item1.price)+(this.item2.quantity * this.item2.price)+(this.item3.quantity * this.item3.price)
        },
        updateQuantity(mode,item){
            if (mode === "minus"){
                item.quantity--
            }
            else{
                item.quantity++
            }
        }
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;700;900&display=swap');
.main-wrap{
    display: inline-flex;
    flex-direction: column;
    font-family: Source Sans Pro;
    font-weight: 400;

    .item, .total{
        min-width: 20rem;
        margin: 0.5rem;
        padding: 1rem;
    }

    .item{
        display: inline-flex;
        align-items: center;
        background-color: #eee;
        border-radius: 0.5rem;

        .quantity{
            margin-right: 1rem;
        }

        .price{
            margin-left: auto;
        }

        .plusminus{
            display: flex;

            div{
                background-color: #ccc;
                padding: 0.5rem 1rem;
                margin-left: 0.5rem;
                border-radius: 0.25rem;
                cursor: pointer;
            }
        }
    }

    .total{
        display: flex;
        justify-content: space-between;
        background-color: #888;
        color: #fff;
        font-weight: 700;
        border-radius: 0.5rem;
    }
}
</style>