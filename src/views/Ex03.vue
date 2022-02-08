<template>
  <div>
    <div>
      <input type="number" v-model.number="num1" />+
      <input type="number" v-model.number="num2" />=
      {{ total }}
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private num1 = 0;
  private num2 = 0;

  get total(): number {
    return Number(this.num1) + Number(this.num2);
  }
}
</script>

<style scoped></style>
