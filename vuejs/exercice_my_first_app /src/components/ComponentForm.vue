<script>
import debounce from "lodash";

export default {
  data() {
    return {
      fullname: "",
      gender: "",
      formData: {
        fullname: "",
        gender: "",
        count: 0,
      },
    };
  },
  methods: {
    Submit: debounce(function () {
      this.formData.fullname = this.fullname;
      this.formData.gender = this.gender;
      this.formData.count++;
    }, 3000),
  },
  // 首次点击提交按钮会立即执行一次Debounce方法，后面3s内不触发事件才能继续执行。这很适合防止表单重复提交
};
</script>

<template>
  <div>
    <div>
      <div>
        <span class="form-label">fullname</span
        ><input type="text" v-model="fullname" />
      </div>
      <div class="form-group">
        <span class="form-label">Gender</span
        ><input id="radio1" type="radio" v-model="gender" value="male" /><label
          for="radio1"
          >male</label
        ><input
          id="radio2"
          type="radio"
          v-model="gender"
          value="female"
        /><label for="radio2">female</label>
      </div>
      <div class="form-ft">
        <button @click="Submit">Submit</button>
      </div>
    </div>
    <div class="form-res">
      <h5>After submission</h5>
      <p>Number of submissions:{{ formData.count }}</p>
      <p>Fullname:{{ formData.fullname }}</p>
      <p>Gender:{{ formData.sex }}</p>
    </div>
  </div>
</template>
