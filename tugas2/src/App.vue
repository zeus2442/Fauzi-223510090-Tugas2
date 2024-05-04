<template>
  <div id="app">
    <h1>{{ greeting }}</h1>
    <p>{{ message }}</p>
    <input
      type="text"
      v-model="inputText"
      placeholder="Masukkan pesan baru"
      style="margin-bottom: 10px"
    />
    <button
      @click="changeMessage"
      :class="{
        'primary-button': inputText !== '',
        'secondary-button': inputText === '',
      }"
      :style="{
        'font-weight': inputText !== '' ? 'bold' : 'normal',
        color: inputText !== '' ? 'white' : 'black',
        display: 'block',
        margin: '0 auto',
      }"
    >
      Ubah Pesan
    </button>
    <button @click="resetMessage">Delete</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      greeting: "WELCOME",
      message: "silahkan masukkan pesan dan kesan anda",
      inputText: "",
    };
  },
  methods: {
    changeMessage() {
      this.message =
        this.inputText !== "" ? this.inputText : "Pesan telah diubah!";
      this.inputText = "";
    },
    resetMessage() {
      this.message = "silahkan masukkan pesan dan kesan anda";
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin-top: 20px;
  background-image: url("./assets/background1.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}

.primary-button {
  background-color: green;
}

.secondary-button {
  background-color: cadetblue;
}

button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 10px;
}
</style>
