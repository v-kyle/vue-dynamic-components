<template>
  <main>
    <keep-alive>
      <component :is="forms[step].component"></component>
    </keep-alive>
    <Steps @input="updateStep" />
  </main>
</template>

<script lang="ts">
import Vue from 'vue';
import Steps from '@/components/Steps.vue';
import Form1 from '@/components/Form1.vue';
import Form2 from '@/components/Form2.vue';
import Form3 from '@/components/Form3.vue';
import EndStepForm from '@/components/EndStepForm.vue';

export default Vue.extend({
  name: 'Home',

  components: { Steps, Form1, Form2, Form3, EndStepForm },

  data() {
    return {
      step: 0,
    };
  },

  methods: {
    updateStep(v: number) {
      this.step = v;
    },
  },

  computed: {
    forms(): object {
      return [
        {
          name: 'Form1',
          component: Form1,
        },
        {
          name: 'Form2',
          component: Form2,
        },
        {
          name: 'Form3',
          component: Form3,
        },
        {
          name: 'End',
          component: EndStepForm,
        },
      ];
    },
  },
});
</script>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

main > * {
  margin-top: 50px;
}
</style>
