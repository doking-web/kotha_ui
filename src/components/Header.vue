<template>
<div>
  <div class="clear"></div>
  <div id="nav">
    <div id="menu"> <img src="@/assets/icons/Menu.svg" alt="Menu"> </div>
    <div id="logo">{{ msg }}</div>
    <div id="more"> <img src="@/assets/icons/More.svg" alt="More"> </div>
  </div>
</div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Header extends Vue {
  @Prop() private msg!: string;
}
</script>

<style lang="scss" scoped>
  
  .clear{
    height: 50px;
  }
  #nav{
    z-index: 1;
    position: fixed;
    top:0;
    width: 100%;
    height: 50px;
    background: var(--color-light-gray);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px;

    #menu{
      align-self: center;
      justify-self: flex-start;
    }

    #logo{
      align-self: center;
      justify-self: center;
      text-align: center;
      color: var(--color-primary);
      text-transform: uppercase;
      font-weight: bold;
      font-size: 18px;

    }

    #more{

    }

  }


</style>
