<template>
<div>

    <div :class="`clear ${from}`">
    <div class="messege">
      <p class="msg">{{ msg }}</p>
      <p class="time">{{ time }}</p>
    </div>
    </div>

  </div>
</template>

<style lang="scss" scoped>
.clear {
  display: flex;
  padding: 5px 10px;
  // flex-direction: vartical;
}

.clear.self {
  justify-content: flex-end;


  .messege {
    border-radius: 8px 0 8px 8px;
    background: var(--color-primary);
  }
}

.clear.other {
  .messege {
    border-radius: 0 8px 8px 8px;
    background: rgb(180, 130, 122);
  }
}

.messege {
    width: fit-content;
    height: fit-content;
    color: #fdfdfd;
    position: relative;
    padding: 10px;
    border-radius: 4px;
    max-width: 400px;

  .msg {
      text-align: left;
      font-size: 1em;
      font-weight: 500;
      width: 100%;
      padding-right: 20px;
      // color: black;
  }
  .time {
      text-align: right;
      font-size: .8em;
      color: #ccc;
      width: 100%;
  }
}
</style>


<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class Messege extends Vue {
  @Prop() private msg: string;
  @Prop() private time: string;
  @Prop() private from: string;
}
</script>


