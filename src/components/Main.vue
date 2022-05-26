<template>
  <div id="app">
    <button class="button" @click="showModal = true">Show Modal</button>
    <transition name="fade" appear>
      <div
        class="modal-overlay"
        v-if="showModal"
        @click="showModal = false"
      ></div>
    </transition>
    <transition name="slide" appear>
      <div class="modal" v-if="showModal">
        <div id="inside">
          <div id="select-langauge"></div>
          <div id="words">
            <center>
              <h1>Make custom Wordle</h1>
              <p>Word can be of any length</p>
            </center>
          </div>
          <div id="input-word">
            <input
              type="text"
              placeholder="Enter Custom Wordle"
              v-model="customWordle"
            />
          </div>
          <div id="generate-or-random">
            <p>Generate Link</p>
            <h3>OR</h3>
            <p>Play Random Word</p>
          </div>
        </div>
        <button class="button" @click="showModal = false">Close Modal</button>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showModal: true,
      customWordle: "",
      played: false,
    };
  },
  methods: {
    Submit() {},
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "montserrat", sans-serif;
}

#app {
  position: relative;

  display: flex;
  justify-content: center;
  align-items: center;

  width: 100vw;
  min-height: 100vh;
  overflow-x: hidden;
}

.button {
  appearance: none;
  outline: none;
  border: none;
  background: none;
  cursor: pointer;

  display: inline-block;
  padding: 15px 25px;
  background-image: linear-gradient(to right, #CC2E5D, #FF5858);
  border-radius: 8px;

  color: #FFF;
  font-size: 18px;
  font-weight: 700;

  box-shadow: 3px 3px rgba(0, 0, 0, 0.4);
  transition: 0.4s ease-out;
}

.button:hover {
  box-shadow: 6px 6px rgba(0, 0, 0, 0.6);
}

.modal-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 98;
  background-color: rgba(0, 0, 0, 0.3);
}

.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 99;

  width: 100%;
  max-width: 400px;
  background-color: #FFF;
  border-radius: 16px;

  padding: 25px;
}
h1 {
  color: #222;
  font-size: 32px;
  font-weight: 900;
  margin-bottom: 15px;
}

p {
  color: #666;
  font-size: 18px;
  font-weight: 400;
  margin-bottom: 15px;
}

.fade-enter-active,
.fade-leave-active {
}

.fade-enter,
.fade-leave-to {
}

.slide-enter-active,
.slide-leave-active {
}

.slide-enter,
.slide-leave-to {
  /*transform: translateX(-50%) translateY(100vh); */
}
</style>