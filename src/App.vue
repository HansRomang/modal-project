

<template>
<h1>{{title}}</h1>
<p>Welcome...</p>
<teleport to=".modals" v-if="showModal">
	<Modal :header=header text="get your ninja swag here" :theme=theme @close="toggleModal">
		<template v-slot:links><a href="#">sign up here!</a><a href="#">more info...</a></template>
		<h1>Giveaway!</h1>
		<p>Get your swag here. </p>
		
	</Modal>
</teleport>
<div v-if="showModalTwo && showModal==false">
	<Modal header="Here's Hans's header!" text="Wow, incredible!" :theme=theme @close="toggleModalTwo">
		<template v-slot:links><a href="#">sauce up here!</a><a href="#">more inc...</a>
		</template>
		<h1>Here's Hans's header!</h1>
		<p>Wow, incredible.</p>
		
	</Modal>
	</div>
<button @click="toggleModal">Open Modal</button>
<button @click="toggleModalTwo">Open Modal Two</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
	name: 'App',
	components:{ Modal },
	data(){
		return{
			title:"my first vue app.",
			header:"Sign up for a free giveaway!",
			theme:"sale",
			showModal:false,
			showModalTwo:false
		}
	},
	methods:{
		handleClick(){
			console.log(this.$refs);
			this.$refs.name.classList.add("active");
		},
		toggleModal(){
			this.showModal = !this.showModal
		},
		toggleModalTwo(){
			this.showModalTwo = !this.showModalTwo
		}
	}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1{
	border-bottom: 1px solid #ddd;
	display:inline-block;
	padding-bottom: 10px;
}

</style>
