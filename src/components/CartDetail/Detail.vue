<template>
  <v-container>
    <v-row>
      <!-- Hình ảnh sản phẩm -->
      <v-col cols="12" md="6">
        <v-carousel>
          <v-carousel-item>
            <v-img
              src="https://via.placeholder.com/400"
              alt="Product Image"
            ></v-img>
          </v-carousel-item>
        </v-carousel>

        <v-row>
          <v-col cols="3">
            <v-img
              src="https://via.placeholder.com/100"
              alt="Thumbnail"
            ></v-img>
          </v-col>
          <v-col cols="3">
            <v-img
              src="https://via.placeholder.com/100"
              alt="Thumbnail"
            ></v-img>
          </v-col>
        </v-row>
      </v-col>

      <!-- Thông tin sản phẩm -->
      <v-col cols="12" md="6">
        <v-chip color="green" label>In Stock</v-chip>
        <h2>Cute Soft Teddybear</h2>
        <p><del>$175</del> <strong>$200</strong></p>
        <v-rating value="4.5" color="yellow"></v-rating>
        <p>236 reviews</p>

        <v-row>
          <v-col>
            <span>Colors:</span>
            <v-btn small color="#FF5733"></v-btn>
            <v-btn small color="#33FF57"></v-btn>
            <v-btn small color="#3357FF"></v-btn>
          </v-col>
        </v-row>

        <v-row>
          <v-col>
            <!-- Nút giảm số lượng -->
            <v-btn icon @click="decreaseQuantity">-</v-btn>

            <!-- Input số lượng với v-model -->
            <v-text-field type="number" v-model="quantity" solo></v-text-field>

            <!-- Nút tăng số lượng -->
            <v-btn icon @click="increaseQuantity">+</v-btn>
          </v-col>
        </v-row>

        <v-row>
          <v-btn color="orange">Buy Now</v-btn>
          <v-btn color="blue">Add To Cart</v-btn>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      quantity: 1,
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
