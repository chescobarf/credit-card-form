<template>
  <button>
    <slot></slot>
  </button>
</template>

<script setup></script>

<style scoped>
button {
  all: unset;
  color: var(--white);
  padding: 1rem;
  background-color: var(--Very--dark--violet);
  appearance: none;
  border: 0;
  border-radius: 10px;
  text-align: center;
  margin-top: 10px;
}
button:hover {
  cursor: pointer;
}
</style>
