<template>
  <div class="steps">
    <el-steps :active="active" finish-status="success">
      <el-step title="Step 1" />
      <el-step title="Step 2" />
      <el-step title="Step 3" />
    </el-steps>
    <div class="btn-container">
      <el-button v-show="active > 0" style="float: left" @click="previous">
        Previous step
      </el-button>
      <el-button v-show="active <= 2" style="float: right" @click="next">
        Next step
      </el-button>
    </div>
  </div>
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
  name: 'Steps',
  data() {
    return {
      active: 0,
    };
  },

  methods: {
    previous() {
      this.active--;
    },

    next() {
      this.active++;
    },
  },

  watch: {
    active(v) {
      this.$emit('input', v);
    },
  },
});
</script>

<style scoped>
.steps {
  width: 400px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.btn-container {
  padding: 0 5px;
  margin-top: 12px;
}

.btn-container > * {
  width: 150px;
  font-weight: bold;
}
</style>
