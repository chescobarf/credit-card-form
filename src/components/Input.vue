<template>
  <div class="input">
    <span class="title uppercase">{{ title }}</span>
    <template v-if="type == 'card-name'">
      <input
        type="text"
        placeholder="e.q. Jane Appleseed"
        @keyup="handlerInput"
      />
    </template>
    <template v-if="type == 'card-number'">
      <input
        type="text"
        :class="{ inputError: error }"
        placeholder="e.g. 1234 5678 9123 0000"
        @keyup="handlerInput"
      />
      <p class="errorMessage">Wrong format, numbers only</p>
    </template>
    <template v-if="type == 'card-cvc'">
      <input
        type="text"
        :class="{ inputError: error }"
        placeholder="e.g. 123"
        @keyup="handlerInput"
      />
      <p class="errorMessage">Can't be blank</p>
    </template>
    <template v-if="type == 'card-exp'">
      <div class="grid grid-cols-2 gap-3">
        <input type="text" :class="{ inputError: error }" placeholder="MM" />
        <input type="text" :class="{ inputError: error }" placeholder="YY" />
      </div>
      <p class="errorMessage">Can't be blank</p>
    </template>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps({
  title: String,
  type: String,
});
const error = ref(true);

const emit = defineEmits(["update:input"]);

function handlerInput(e) {
  emit("update:input", e.target.value);
}
</script>

<style scoped>
.input {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.input .title {
  color: var(--Very--dark--violet);
}
input {
  padding: 1rem;
  border: 1px solid var(--light-grayish-violet);
  border-radius: 10px;
}
input:focus-visible {
  outline: none !important;
  border-color: var(--gradient-color);
}
.inputError,
.inputError:focus-visible {
  border-color: var(--red-error);
}
.errorMessage {
  font-size: 14px;
  color: var(--red-error);
}
</style>
