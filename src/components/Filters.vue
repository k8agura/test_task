<template>
  <div class="Filters">
    <div class="container d-flex align-items-center justify-content-start">
    <h3 class="title text-center text-dark ">Страны</h3>
    </div>
    <div class="form-check mt-2" v-for="option in options">
      <input class="form-check-input" type="radio"
             :value="option.value"
             v-model="modelValue"
             @change="getChanges">
      <label class="form-check-label"><h4>{{option.name}}</h4></label>
    </div>
  </div>
</template>
<script>
export default {
  name: "Filters",
  props: {
    options: {
      type: Array,
      required: true,
    },
    modelValue: {
      type: String
    },
  },
  methods: {
    getChanges(event) {
      this.$emit('update:modelValue', event.target.value);
    }
  },
  data() {
    return {}
  },
}
</script>

<style>

</style>