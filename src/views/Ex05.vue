<template>
  <div id="context">
    <div class="caveat">{{ caveatInputName }}</div>
    <div><label for="name">名前：</label></div>
    <div><input type="text" id="name" v-model="name" /></div>

    <div class="caveat">{{ caveatInputAge }}</div>
    <div><label for="age">年齢：</label></div>
    <div><input type="number" id="age" v-model="age" /></div>

    <div class="caveat">{{ caveatInputComment }}</div>
    <div><label for="comment">コメント：</label></div>
    <textarea id="comment" cols="30" rows="10" v-model="comment"></textarea>

    <div><button type="button" @click="inputCheck">入力値チェック</button></div>
    <hr />

    <div class="caveat">{{ completeSend }}</div>
    <div>入力値：</div>
    <div>名前：{{ name }}</div>
    <div>年齢：{{ age }}</div>
    <div>コメント：{{ comment }}</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class XXXComponent extends Vue {
  private name = "";
  private age = "";
  private comment = "";
  private caveatInputName = "";
  private caveatInputAge = "";
  private caveatInputComment = "";
  private completeSend = "";

  inputCheck(): void {
    if (this.name === "") {
      this.caveatInputName = "名前が入力されていません";
    } else {
      this.caveatInputName = "";
    }
    if (this.age === "") {
      this.caveatInputAge = "年齢が入力されていません";
    } else {
      this.caveatInputAge = "";
    }
    if (this.comment === "") {
      this.caveatInputComment = "コメントが入力されていません";
    } else {
      this.caveatInputComment = "";
    }
    if (
      this.caveatInputName === "" &&
      this.caveatInputAge === "" &&
      this.caveatInputComment === ""
    ) {
      this.completeSend = "送信完了";
    }
  }
}
</script>

<style scoped>
#context {
  text-align: left;
  border: solid blue;
}

.caveat {
  color: red;
}
</style>
