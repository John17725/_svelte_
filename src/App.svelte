<script>
	import About from "./components/About.svelte"
	import Text from "./components/Text.svelte"
	import Person from "./components/Person.svelte"
	import Skills from "./components/Skills.svelte"
	import Input from "./components/Input.svelte"

	import { dataset_dev } from "svelte/internal";

	export let name;
	export let LastName;
	let svelteLogo = "https://arepa.s3.amazonaws.com/svelte-logo.png";


	const data = {
		name: "Jesus",
		lastName: "Gonzalez",
		age: 22,
	}
</script>

<main>
	<h1>Hello {name} {LastName}!</h1>
	<About />
	<Text anotherText="Hola!!" />
	<Text />
	<Person {...data}/>
	<Skills />
	<Input />		
	<img src={svelteLogo} alt="Svelte">
</main>

<style>

	/* Estilos globales */
	:global(body){
		background-color: #f2eee2;
		color: #0084f6;
	}

	:global(body.dark-mode){
		background-color: #1d3040;
		color: #bfc2c7;
	}

	:global(:root){
		--theme-color: #800080;
		
	}


	main img{
		width: 30%;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>