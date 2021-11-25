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
</div>

<style lang="scss">
	#Actu {
		width: 65%;
		overflow-y: scroll;
		margin-bottom: 24px; 

		&::-webkit-scrollbar {
  			display: none;
		}
	}
	
</style>
