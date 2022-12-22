<template>
  <!-- <appInitial /> -->

  <div class="container">
    <component
      :is="screens[position]"
      @goto="handleGoTo"
      @question="handleQuestion"
    />
  </div>
</template>

<script>
import appInitial from './components/Initial.vue';
import appConfirm from './components/Confirm.vue';
import appResult from './components/Result.vue';

export default {
  components: {
    appInitial,
    appConfirm,
    appResult,
  },
  data() {
    return {
      screens: ['appInitial', 'appConfirm', 'appResult'],
      position: 0,
      question: '',
    };
  },
  methods: {
    handleGoTo(position) {
      this.position = position;
    },
    handleQuestion(question) {
      this.question = question;
    },
  },
};
</script>

<style>
@import './assets/style.css';
</style>
