<template>
  <div class="context">
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}歳</div>
    <div>10年後の年齢：{{ agePlus10 }}歳</div>
    <div>
      趣味：<span v-for="hobby of hobbies" :key="hobby">{{ hobby }} </span>
    </div>
    <div></div>
    <div>
      <a :href="link" @click="addStatus">自社ページリンク</a>
    </div>
    <div>
      <img :src="img" alt="" />
    </div>
    <div>
      <button type="button" :disabled="button">ボタン</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "";
  private age = 0;
  private hobbies = Array<string>();
  private link = "";
  private img = "";
  private button = true;

  get agePlus10(): number {
    return this.age + 10;
  }

  addStatus(): void {
    this.name = "野口拓也";
    this.age = 24;
    this.hobbies = ["スイム", "バイク", "ラン"];
    this.link = "#";
    this.img = "/pagu.jpg";
    this.button = false;
  }
}
</script>

<style scoped>
.context {
  border: solid red;
  text-align: left;
}
</style>
