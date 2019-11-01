<template>
  <div :height="height" :width="width" class="home">
    <Header msg="Conversations" />
    <div class="scroll-view">
      <Conversation />
      <Conversation />
      <Conversation />
      <Conversation />
      <Conversation />
      <Conversation />
      <Conversation />
      <Conversation />
      <Conversation />
      <Conversation />
    </div>
    <Footer />
  </div>
</template>

<style scoped lang="scss">
.home {
  display: grid;
}
.scroll-view{
  overflow-y: scroll;
}
</style>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import Conversation from '@/components/Conversation.vue';

@Component({
  components: {
    Header,
    Footer,
    Conversation,
  },

})
export default class Home extends Vue {
  private height: number = 0;
  private width: number = 0;
  protected created() {
    this.height = window.innerHeight;
    this.width = window.innerWidth;

    console.log(this)
  }
}
</script>
