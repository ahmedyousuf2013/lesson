<template>
  <div>
    <span v-for="item in plans" v-bind:key="item">
      {{ item }}
    </span>
  </div>
</template>

<script>
export default {
  props: ["name"],

  data() {
    return {
      plans: ["plan 1 ", "plan 2 ", "plan 3"],
    };
  },
};
</script>