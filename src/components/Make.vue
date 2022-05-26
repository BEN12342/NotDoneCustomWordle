<template>
  <center>
    <h1>Custom Wordle</h1>
    <div id="heading">
      <svg
        id="i"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        aria-hidden="true"
        class="h-7 w-7 cursor-pointer"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
        ></path>
      </svg>
      <button id="MakeOwn" @click="showModal = true">
        Make your own Wordle
      </button>
      <transition name="fade" appear>
        <div class="modal-overlay" v-if="showModal"></div>
      </transition>
      <svg
        id="stats"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        aria-hidden="true"
        class="h-7 w-7 cursor-pointer"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"
        ></path>
      </svg>
    </div>
  </center>
</template>

<script>
export default {
  data() {
    return {
      showModal: true,
    };
  },
  methods: {
    popUp() {},
  },
};
</script>

<style scoped>
#heading {
  display: grid;
  grid-template-columns: auto auto auto;
  transform: translate(10px);
}

svg {
  height: 40px;
}

#MakeOwn {
  transform: translate(125px, -13px);
}

#i {
  transform: translate(95px, 0px);
}

#stats {
  transform: translate(150px);
}
</style>