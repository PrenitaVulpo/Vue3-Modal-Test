<template>
  <img alt="Vue logo" src="./assets/logo.png">
	<h1>{{ tittle }}</h1>
	<p>Welcome...</p>

		<teleport to="#modal" v-if="showModal">
			<Modal :header="header" :text="text" theme="sale" @close="toggleModal">
				<template v-slot:links>
					<a href="#">sign up now</a>
					<a href="#">more info</a>
				</template>
				<h1>Ninja Givaway!</h1>
				<p>Grab your ninja swag for half price!</p>
			</Modal>
		</teleport>

		<teleport to="#modal" v-if="showModal2">
			<Modal :header="header" :text="text" @close="toggleModal2">
				<template v-slot:links>
					<a href="#">New Link</a>
				</template>
			</Modal>
		</teleport>
	<button @click="toggleModal">Open modal</button>
	<button @click="toggleModal2">Open modal 2</button>

</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "Vue app",
      header: "Modal2",
      text: "MOdal2 text",
      showModal: false,
			showModal2: false,
    };
  },
	methods: {
		toggleModal() {
			this.showModal = !this.showModal
		},
		toggleModal2() {
			this.showModal2 = !this.showModal2
		},
	}
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
	width: 100%;
	height: 100%;
}
</style>
