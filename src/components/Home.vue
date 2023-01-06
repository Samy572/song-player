<template>
	<h1>Player</h1>
  <div class="container">
    <div class="pacco" v-for="(product, index) in products" :key="product.id" >
      <img class="coverPacco" :src="product.cover" :alt="product.name" />
      <button class="player" >
        <i
		@click="selectedProduct[index] = !selectedProduct[index]"
          :class="{ 'fa-regular fa-circle-play': selectedProduct[index] === true, 'far fa-pause-circle': selectedProduct[index] === false }"
        ></i>
      </button>
      <h2>{{ product.name }}</h2>
      <p>{{ product.title }}</p>
    </div>
  </div>
</template>


<script lang="ts">
import { ref } from "@vue/reactivity";
import { products } from "../interfaces/musiques";

export default {
  setup() {
	const selectedProduct = ref(Array(products.length).fill(true));


    return {
      selectedProduct,
      products,
    };
  },
};
</script>

<style scoped lang="scss">
@import "../scss/base.scss";
h1 {
  text-align: center;
  font-size: 4em;
  padding-top: 15px;
}

.container {
  margin-top: 120px;
  height: auto;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.pacco {
  position: relative;
}

.coverPacco {
  height: 220px;
  width: 220px;
  margin-bottom: 20px;
  object-fit: cover;
  overflow: hidden;
  -webkit-box-shadow: 1px 1px 15px 5px #4d4848;
  box-shadow: 1px 1px 15px 5px #4d4848;
 
  &:hover {
    
    cursor: pointer;
  }
}

.player {
 
  cursor: pointer;
  position: absolute;
  bottom: 40%;
  right: 10%;
  opacity: 0.6;
  padding: 0;
  outline: none;
  border-radius: 50%;
  border: transparent;
  i {
	z-index: 1;
	border-radius: 50%;
    color: rgb(222, 34, 34);
    font-size: 2.7em;
	transition: all 0.5s ease;
	&:hover{
		transform: scale(1.3);
	}
  }
}
</style>
