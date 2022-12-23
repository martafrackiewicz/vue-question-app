<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1>Ask a question</h1>
    <div class="mb-3">
      <input
        name="question"
        type="text"
        class="form-control"
        id="question"
        v-model="question"
      />
      <button
        class="btn animate__animated animate__fadeIn"
        v-if="question"
        @click="handleNext"
      >
        Next
      </button>
      <div v-if="error" class="error">Your question is too short</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: '',
      error: false,
    };
  },
  methods: {
    handleNext(e) {
      e.preventDefault();

      if (this.question.length <= 2) {
        this.error = true;
      } else {
        this.error = false;
        this.$emit('goto', 1);
        this.$emit('question', this.question);
      }
    },
  },
};
</script>

<style></style>
