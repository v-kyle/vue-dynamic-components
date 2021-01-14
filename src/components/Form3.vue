<template>
  <div>
    <h2>Form 3</h2>
    <el-form :inline="true" :model="formInline" class="demo-form-inline">
      <el-form-item label="Approved by">
        <el-input
          v-model="formInline.user"
          placeholder="Approved by"
        ></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary">Click</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name: 'Form3',

  data() {
    return {
      formInline: {
        user: '',
      },
    };
  },
};
</script>
