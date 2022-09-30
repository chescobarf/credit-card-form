<template>
  <div class="background">
    <div class="bg-img"></div>
    <div class="content">
      <div class="content_left">
        <Cards :name="name" :number="number" :exp="exp" :cvc="cvc" />
      </div>
      <div class="content_right">
        <Input
          title="CARDHOLDER Name"
          type="card-name"
          @update:input="handleName"
        />
        <Input
          title="Card Number"
          type="card-number"
          @update:input="handleNumber"
        />
        <div class="grid grid-cols-2 gap-6">
          <Input
            title="EXP. DATE (MM/YY)"
            type="card-exp"
            @update:input="handleEXP"
          />
          <Input title="cvc" type="card-cvc" @update:input="handleCVC" />
        </div>
        <Button>Confirm</Button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Button from "./components/Button.vue";
import Input from "./components/Input.vue";
import Cards from "./components/Cards.vue";

const name = ref("JANE APPLESEED");
const number = ref("1234 5678 9123 0000");
const exp = ref("01/12");
const cvc = ref("000");

const handleName = (e) => (name.value = e);
const handleNumber = (e) => (number.value = e);
const handleCVC = (e) => (cvc.value = e);
const handleEXP = (e) => (exp.value = e);
</script>

<style scoped>
.background {
  width: 100%;
  height: 100vh;
}
.bg-img {
  background-image: url(./images/bg-main-desktop.png);
  width: 30%;
  height: 100%;
  z-index: 0;
  position: fixed;
  background-position: center;
  background-size: cover;
}
.content {
  gap: 5rem;
  position: relative;
  display: grid;
  place-content: center;
  z-index: 1;
  height: 100%;
  grid-template-columns: 1fr 1fr;
  margin: 0 auto;
  width: 80%;
}
.content_left {
}
.content_right {
  display: flex;
  gap: 2rem;
  flex-direction: column;
  justify-content: center;
}
</style>
