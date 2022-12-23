<template>
  <!-- <appInitial /> -->

  <div class="container">
    <transition name="fade" appear mode="out-in">
      <component
        :is="screens[position]"
        :question="question"
        @goto="handleGoTo"
        @question="handleQuestion"
    /></transition>
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

.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: 0.5s;
}
.fade-enter-to {
  opacity: 1;
}
.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: 0.5s;
}
.fade-leave-to {
  opacity: 0;
}
</style>
