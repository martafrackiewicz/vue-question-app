<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h3>Your answer is:</h3>
    <div class="viewer">{{ result }}</div>

    <div class="animate__animated animate__bounceIn animate__delay-1s">
      <hr />
      <button class="btn" @click="startOver">Start over</button>
      <button class="btn" @click="getResult">Decide again</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    result: String,
  },
  mounted() {
    this.getResult();
    // this.$emit('showResult');
  },
  methods: {
    startOver() {
      this.$emit('startOver');
    },
    getResult() {
      this.$emit('showResult');
    },
  },
};
</script>

<style></style>
