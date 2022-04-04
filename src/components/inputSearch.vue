<template>
  <div class="d-flex align-items-end justify-content-end">
  <input type="text" class="form-control w-100" v-model="input"  @input="changeInput">
    <button class="btn btn-outline-secondary" type="button" id="button-addon2">Искать</button>
  </div>
</template>

<script>
export default {
  name: "inputSearch",
  props:{
    input: {
      type: String
    }
  },
  methods: {
    changeInput(event) {
      this.$emit('update:modelValue', event.target.value);
    }
  },
}
</script>

<style scoped>

</style>