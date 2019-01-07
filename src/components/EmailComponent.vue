<template>

  <q-input
  class="formBackground moreCenterT"
  v-model="password"
  type="password"
  :before="[{icon: 'lock', handler () {}}]"
  placeholder="password"
  :class="{ hasError: v.$error }"
   />
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ""
    },
    v: {
      type: Object,
      required: true
    }
  },
  computed: {
    password: {
      get() {
        return this.value;
      },
      set(value) {
        this.v.$touch();
        this.$emit("input", value);
      }
    }
  }
};
</script>

<style media="screen">
.moreCenterT{
  margin-top:-10vh;

}
</style>
