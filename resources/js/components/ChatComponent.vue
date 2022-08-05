<template>
  <div class="bg-grey">
    <div style="overscroll-behavior: none">
      <!-- HEADING -->
      <div
        class="
          fixed
          w-full
          bg-slate-800
          h-16
          p-2
          text-white text-center
          flex
          shadow-md
        "
        style="top: 0px; overscroll-behavior: none"
      >
        <div
          class="my-3 text-white font-bold text-lg text-center tracking-wide"
        >
          Laravel Lex Chat Bot
        </div>
      </div>

      <!-- MESSAGES -->
      <div class="mt-20 mb-16 box-message">
        <!-- SINGLE MESSAGE 3 -->
        <div class="clearfix" v-for="item in items">
          <div
            class="
              bg-teal-900
              float-right
              w-3/4
              mx-4
              my-2
              p-2
              rounded-lg
              clearfix
              text-white
            "
          >
            {{ item[0] }}
          </div>
        </div>

        <!-- SINGLE MESSAGE 3 -->
        <div class="clearfix">
          <div
            class="
              text-white
              bg-slate-600
              float-left
              w-3/4
              mx-4
              my-2
              p-2
              rounded-lg
              clearfix
            "
          >
            Welcome to Laravel Lex Chat Bot !
          </div>
        </div>
      </div>
    </div>

    <!-- MESSAGE INPUT AREA -->
    <div
      class="fixed w-full flex justify-between bg-slate-800"
      style="bottom: 0px"
    >
      <input
        v-model="msg"
        v-on:keyup.enter="entersendmessage"
        type="text"
        class="
          flex-grow
          m-2
          p-4
          
          placeholder-white
          text-white
          rounded-md
          border border-slate-500
          bg-slate-500
          resize-none
        "
        rows="1"
        placeholder="Write message here"
        style="outline: none"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "",
      items: [],
    };
  },
  methods: {
    sendmessage() {
        if(this.msg.length>0){
   this.item = [this.msg];
      this.items.push(this.item);
        }
    },
    entersendmessage: function(e) {
      if (e.keyCode === 13) {
        if(this.msg.length>0){
          this.item = [this.msg];
          this.items.push(this.item);
          this.msg = '';
        }
      }    
    },
  },
};
</script>