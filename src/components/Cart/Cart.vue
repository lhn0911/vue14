<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="8">
        <v-card>
          <v-card-title>Item Cart</v-card-title>
          <v-card-subtitle>Product Summary</v-card-subtitle>

          <v-row>
            <v-col cols="4">
              <v-img
                src="https://via.placeholder.com/100"
                alt="Product Image"
              ></v-img>
            </v-col>
            <v-col cols="4">
              <div>Cute Soft Teddybear</div>
              <div>Size: 8 | Color: Dark Red</div>
            </v-col>
            <v-col cols="2">
              <!-- Nút giảm số lượng -->
              <v-btn icon @click="decreaseQuantity">-</v-btn>

              <!-- Input số lượng với v-model -->
              <v-text-field
                type="number"
                v-model="quantity"
                solo
                min="1"
              ></v-text-field>

              <!-- Nút tăng số lượng -->
              <v-btn icon @click="increaseQuantity">+</v-btn>
            </v-col>
            <v-col cols="2">
              <span>$200</span>
              <v-btn icon>
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-col>
          </v-row>
        </v-card>

        <v-row>
          <v-btn color="blue">Continue Shopping</v-btn>
          <v-btn color="orange">Checkout</v-btn>
        </v-row>
      </v-col>

      <v-col cols="12" md="4">
        <v-card>
          <v-card-title>Order Summary</v-card-title>
          <v-list-item>
            <v-list-item-content>Sub Total</v-list-item-content>
            <v-list-item-content>$200</v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content>Discount</v-list-item-content>
            <v-list-item-content>- $10</v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content>Total</v-list-item-content>
            <v-list-item-content>$190</v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      quantity: 1, // Biến quantity được liên kết với v-model
    };
  },
  methods: {
    increaseQuantity() {
      this.quantity++;
    },
    decreaseQuantity() {
      if (this.quantity > 1) {
        this.quantity--;
      }
    },
  },
};
</script>
