<template>
  <div>
    <div>
      <input type="number" v-model="num1" />+
      <input type="number" v-model="num2" />=
      {{ sum }}
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private num1 = 0;
  private num2 = 0;

  get sum(): number {
    return Number(this.num1) + Number(this.num2);
  }
}
</script>

<style scoped></style>
