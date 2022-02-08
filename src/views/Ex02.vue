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
      <a :href="link">自社ページリンク</a>
    </div>
    <div>
      <img :src="img" />
    </div>
    <div>
      <button type="button" @click="addStatus" :disabled="canNotPush">
        ボタン
      </button>
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
  private canNotPush = false;

  get agePlus10(): number {
    return this.age + 10;
  }

  addStatus(): void {
    this.name = "野口拓也";
    this.age = 24;
    this.hobbies = ["スイム", "バイク", "ラン"];
    this.link = "#";
    this.img = "/pagu.jpg";
    this.canNotPush = true;
  }
}
</script>

<style scoped>
.context {
  border: solid red;
  text-align: left;
}
</style>
