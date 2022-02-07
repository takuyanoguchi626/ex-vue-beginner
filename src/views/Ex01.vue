<template>
  <div>
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}</div>
    <div>10年後の年齢：{{ ageplus10 }}</div>
    <div>
      <span v-for="hob of hobby" :key="hob">{{ hob }}</span>
    </div>
    <div></div>
    <div>
      <a href="#">自社ページリンク</a>
    </div>
    <div>
      <img src="/pagu.jpg" alt="" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "野口拓也";
  private age = 24;
  private hobby = ["スイム", "バイク", "ラン"];

  get ageplus10(): number {
    return this.age + 10;
  }
}
</script>

<style scoped></style>
