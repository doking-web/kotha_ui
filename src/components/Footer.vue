<template>
<div>
    <div class="clear"></div>
    <div id="bottom-nav">
        <div class="nav-item" id="bar"></div>
        <div class="nav-item" id="conversations"> <img src="@/assets/icons/con.svg" alt="Profile Tab"> </div>
        <div class="nav-item" id="feed" > <img src="@/assets/icons/feed.svg" alt="Profile Tab"> </div>
        <div class="nav-item" id="profile"> <img src="@/assets/icons/profile.svg" alt="Profile Tab"> </div>
        <div class="nav-item" id="setings"> <img src="@/assets/icons/settings.svg" alt="Profile Tab"> </div>
    </div>
    </div>
</template>

<style lang="scss" scoped>
.clear{
    height: 50px;
}
#bottom-nav{
    position: fixed;
    display: flex;
    bottom:0;
    background: var(--color-primary);
    justify-content: space-around;
    align-items: center;
    width: 100%;
    height: 50px;

    #bar{
        visibility: hidden;
        position: absolute;
        background: var(--color-acsent);
        top:0;
        width: 60px;
        height: 4px;
        border-radius: 2px;
    }

    .nav-item img{
        width: 30px;
    }
}

</style>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Footer extends Vue {
  @Prop() private active!: string;
}
</script>
