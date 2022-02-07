<template>
  <div class="context">
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}</div>
    <div>10年後の年齢：{{ agePlus10 }}</div>
    <!-- ageplus10をキャメルケースに変更 -->
    <div>
      趣味：<span v-for="hobby of hobbys" :key="hobby">{{ hobby }} </span>
      <!-- hobbyをhobbysに、hobをhobbyに変更 -->
    </div>
    <div></div>
    <div>
      <a :href="link">自社ページリンク</a>
      <!-- リンク先をvueを使って変数名で定義 -->
    </div>
    <div>
      <img :src="img" alt="" />
      <!-- リンク先をvueを使って変数名で定義 -->
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "野口拓也";
  private age = 24;
  private hobbys = ["スイム", "バイク", "ラン"];
  private link = "#";
  private img = "/pagu.jpg";

  get agePlus10(): number {
    return this.age + 10;
  }
}
</script>

<style scoped>
.context {
  border: solid red;
  text-align: left;
}
/* 枠線と左寄せを失念していた。 */
</style>
