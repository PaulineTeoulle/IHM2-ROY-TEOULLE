<script>
	import TopBar from "../components/TopBar.svelte"
	import Post from "../components/Post.svelte"

	let posts = [
		{"user" : "Sxyrp", "thumbnail": "kiwi.jpg", "game" : "Dofus", "message" : "Quête tutu presque terminée !!! Demain gros rush temporis (bougle dj gelé pour drop le gelano) :p", "image" : "tutu.png"},
		{"user" : "Bamboo", "thumbnail": "scratch.jpg", "game" : "Dofus", "message" : "Caverne des Bworks", "image" : "caverne.png"}
	]
</script>


<div id="Actu">
	<TopBar/>
	{#each posts as post}
        <Post post={post}/>
    {/each}
	<div class="background"></div>
</div>

<style lang="scss">
	@import '../styles/color.scss';

	#Actu {
		width: 65%;
		overflow-y: scroll;
		margin-bottom: 24px; 

		&::-webkit-scrollbar {
			display: none;
		}

		.background{
			filter: contrast(.7);
			display: none;
			top: 0;
			left: 0;
			position: absolute;
			width: 100vw;
			height: 100vh;
			background-color: $primary;
			opacity: .5;
			z-index: 1;
		}
	}
	
</style>
