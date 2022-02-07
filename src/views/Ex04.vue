<template>
  <div>
    <div>
      <input type="number" v-model="num1" />
    </div>
    <div>
      <input type="number" v-model="num2" />
    </div>
    <div>
      <input type="number" v-model="num3" />
    </div>
    <div>税抜き価格：{{ priceWithoutTax }}</div>
    <div>税込み価格：{{ priceInTax }}</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private num1 = 0;
  private num2 = 0;
  private num3 = 0;
  private tax = 0.1;

  get priceWithoutTax(): number {
    return Number(this.num1) + Number(this.num2) + Number(this.num3);
  }

  get priceInTax(): number {
    return (
      (Number(this.num1) + Number(this.num2) + Number(this.num3)) *
      (1 + Number(this.tax))
    );
  }
}
</script>

<style scoped></style>
