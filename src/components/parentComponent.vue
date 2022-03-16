<template>
  <VErrorBoundary :on-error="TriggerMe" :fall-back="fallBack">
    <ImUnstable />
  </VErrorBoundary>
</template>

<script>
import { markRaw } from "vue";
import VErrorBoundary from "vue-error-boundary";
import ImUnstable from "./ImUnstable.vue";
import ContactError from "./ContactError.vue";
export default {
  components: {
    ImUnstable,
    VErrorBoundary,
  },
  name: "App",
  data() {
    return {
      fallBack: markRaw(ContactError),
    };
  },
  methods: {
    TriggerMe() {
      console.log("It Triggered");
    },
  },
};
</script>

<style scoped>
</style>
