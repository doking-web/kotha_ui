<template>
  <div class="conversations">
  <router-link class="link" :to=" `msg/${from}`">
    <div class="heading">
      <div class="user">
        <img width="40" src="@/assets/icons/user.svg" alt="Profile" />
      </div>
      <div id="name">{{ name }}</div>
      <div id="time">{{ time }}</div>
    </div>
    <div class="msg">{{ msg }}</div>
    </router-link>
  </div>
</template>

<style lang="scss" scoped>
.conversations {
  // background: #444;
  padding: 10px;
  .heading{
      position: relative;
      display: flex;
    //   justify-content: space-between;
      align-items: center;
      #name{
          margin-left: 10px;
          font-weight: bold;
          font-size: 24px;
      }
      #time{
          position: absolute;
          right: 10px;
      }
  }
  .msg{
      padding: 0 0 0 50px;
      text-align: left;
      text-overflow: ellipsis;
      // max-lines: 1;
      overflow: hidden;
      white-space: nowrap;
      height: 20px;
  }
}
</style>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component
export default class Conversation extends Vue {
  @Prop() from: string = "go";
  @Prop() msg: string  = "Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti itaque saepe maxime, veniam explicabo dolorem totam minima eaque consequatur eligendi.";
  @Prop() name: string = "Hillal Kr. Roy";
  @Prop() time: string = "2d";
}
</script>
