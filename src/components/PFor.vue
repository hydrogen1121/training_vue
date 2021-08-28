<template>
  <!-- <ul>
    <li v-for="(step, i) in steps" :class="{is-active: i < activeIndex}">
      {{ step.text }}
    </li>
  </ul> -->
  <div v-for="(step, index) in steps" :key="(step.message, index)">
    {{ step.message }}
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    activeIndex: Number,
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
});
</script>

<style></style>
