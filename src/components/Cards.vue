<template>
  <div class="flex flex-col gap-8">
    <div class="card-left">
      <img
        src="../images/bg-card-front.png"
        alt=""
        srcset=""
        class="drop-shadow-2xl w-full"
      />

      <div class="logo">
        <img src="../images/card-logo.svg" alt="" />
      </div>
      <div class="number">{{ number }}</div>
      <div class="footer uppercase">
        <p>{{ name }}</p>
        <p>{{ exp }}</p>
      </div>
    </div>
    <div class="card-right">
      <img
        src="../images/bg-card-back.png"
        alt=""
        srcset=""
        class="drop-shadow-2xl w-full"
      />
      <div class="content">{{ cvc }}</div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  name: String,
  number: String,
  exp: String,
  cvc: String,
});
</script>

<style scoped>
.card-left {
  display: flex;
  justify-content: start;
  position: relative;
  margin-right: 3rem;
}
.card-right {
  display: flex;
  justify-content: end;
  position: relative;
  margin-left: 3rem;
}
.card-right .content {
  position: absolute;
  top: 44%;
  right: 15%;
  color: white;
  font-size: 18px;
}
.card-left .logo {
  position: absolute;
  top: 2rem;
  left: 2rem;
}
.card-left .number {
  top: 50%;
  color: var(--white);
  font-size: 1.5rem;
  letter-spacing: 10px;
  margin: 0 auto;
  position: absolute;
  right: 50%;
  transform: translateX(50%);
  width: 100%;
  text-align: center;
}
.card-left .footer {
  position: absolute;
  bottom: 2rem;
  display: flex;
  justify-content: space-between;
  right: 50%;
  width: 100%;
  text-align: center;
  padding: 0px 2rem;
  transform: translateX(50%);
  color: var(--white);
}
</style>
