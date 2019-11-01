<template>
  <div  :height="height" :width="width" class="messeging">
      <div ref="msgs" class="messeges">
        <Messege from="self" time ="02:36 PM" msg="Hi I am hero"/>
        <Messege from="other" time ="02:36 PM" msg="Hi I am hero"/>
        <Messege from="self" time ="02:36 PM" msg="Hi I am hero"/>
        <Messege from="other" time ="02:36 PM" msg="Hi I am hero"/>
        <Messege from="self" time ="02:36 PM" msg="Hi I am hero"/>
        <Messege from="other" time ="02:36 PM" msg="Hi I am hero"/>
        <Messege from="self" time ="02:36 PM" msg="Hi I am hero"/>
        <Messege class="new-msg" from="self" time ="02:36 PM" msg="Hi I am hero"/>

  </div>
  <div class="inputs">
    <form id="form" @submit.prevent="submit">
      <button><img src="@/assets/icons/camera.png" alt="sent"></button>
      <input ref="inputMsg" type="text">
      <button type="submit"><img src="@/assets/icons/send.svg" alt="sent"></button>
    </form>
  </div>
  </div>
</template>

<style lang="scss">
.messeging {
  display: grid;
}
.scroll-view{
  overflow-y: scroll;
}
.inputs{
  display: block;
  position: fixed;
  bottom: 0;
  width: 100%;
  background-color: var(--color-primary);
  padding: 5px;
  #form{
    display: grid;
    grid-template-columns: 30px 1fr 30px;
    grid-column-gap: 5px;
    padding: 0 10px;
    align-items: center;
    width: 100%;
  }
  input, button{
    display: initial;
    height: 30px;
    background: transparent;
    border: none;
    outline: none;
    border: 1px solid var(--color-acsent);
    color: var(--color-acsent);
    padding: 5px;
    border-radius: 5px;
  }
  button{
    border: none;
  }
}
.new-msg{

  animation: enter 300ms ease-in;

}

@keyframes enter {
  0%{
    opacity: 0;
    transform: translateY(100px);
  }
  100%{
    opacity: 100;
    transform: translateY(0);
  }
}


</style>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import Conversation from '@/components/Conversation.vue';
import Messege from '@/components/Messege.vue';

@Component({
  components: {
    Header,
    Footer,
    Conversation,
    Messege,
  },

})
export default class Messaging extends Vue {
  private height: number = 0;
  private width: number = 0;
  protected created() {
    this.height = window.innerHeight;
    this.width = window.innerWidth;
  }


  submit(){
    let el = new Messege({
      propsData:{
        from: "self",
        time: "04:20 AM",
        msg: this.$refs.inputMsg.value
      }
    });
    this.$refs.inputMsg.value = "";
    el.$mount();
    console.log(el);
    el.$el.classList.add("new-msg");
    this.$refs.msgs.appendChild(el.$el);
  }
}
</script>
