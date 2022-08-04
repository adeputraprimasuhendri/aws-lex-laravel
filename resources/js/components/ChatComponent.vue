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
            {{ msg }}
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
        type="text"
        class="
          flex-grow
          m-2
          p-4
          mr-1
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
      <button class="m-2" style="outline: none" @click="sendmessage">
        <svg
          class="
            svg-inline--fa
            text-slate-300
            fa-paper-plane fa-w-16
            w-12
            h-12
            py-2
            mr-2
          "
          aria-hidden="true"
          focusable="false"
          data-prefix="fas"
          data-icon="paper-plane"
          role="img"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 512 512"
        >
          <path
            fill="currentColor"
            d="M476 3.2L12.5 270.6c-18.1 10.4-15.8 35.6 2.2 43.2L121 358.4l287.3-253.2c5.5-4.9 13.3 2.6 8.6 8.3L176 407v80.5c0 23.6 28.5 32.9 42.5 15.8L282 426l124.6 52.2c14.2 6 30.4-2.9 33-18.2l72-432C515 7.8 493.3-6.8 476 3.2z"
          />
        </svg>
      </button>
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
  },
};
</script>