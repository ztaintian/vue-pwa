<template>
  <div class="home">
    <img @click="adddecimalCount" alt="Vue logo" src="../assets/logo.png">
    <HelloWorld  msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Watch, Emit } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
// https://www.cnblogs.com/zyfd/p/9907925.html
@Component({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {
  private  decimal: number = 6;
  private  myThy(): void {
    console.log(this.decimal);
  }
  @Watch('decimal')
  private decimalCount(newValue: string, oldValue: string) {
    console.log(newValue, oldValue);
  }
  @Emit()
  private adddecimalCount(): void {
    this.decimal = 3;
  }
}
</script>
