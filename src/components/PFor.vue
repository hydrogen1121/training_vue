<template>
  <div
    v-for="(step, index) in steps"
    :key="(step.message, index)"
    :class="{ 'is-active': index < allSteps }"
  >
    {{ step.message }}
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    activeIndex: {
      type: Number,
    },
  },
  data() {
    return {
      steps: [
        { message: "アカウント入力" },
        { message: "プラン選択" },
        { message: "支払い設定方法" },
        { message: "登録完了" },
      ],
    };
  },
  setup(activeIndex) {
    const allSteps = (activeIndex = 1);
    console.log(allSteps);
    return {
      allSteps,
    };
  },
});
</script>

<style>
.is-active {
  color: blue;
}
</style>
