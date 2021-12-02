<script>
    import Banner from "../components/Banner.svelte";
	import Post from "../components/Post.svelte";
    import Platform from "../components/Platform.svelte";
    let posts = [
		{"user" : "Sxyrp", "thumbnail": "kiwi.jpg", "game" : "Dofus", "message" : "Quête tutu presque terminée !!! Demain gros rush temporis (bougle dj gelé pour drop le gelano) :p", "image" : "tutu.png"},
		{"user" : "Bamboo", "thumbnail": "scratch.jpg", "game" : "Dofus", "message" : "Caverne des Bworks", "image" : "caverne.png"}
	]
</script>

<div class="Profil">
    <div>
        <Banner/>
        {#each posts as post}
         <Post post={post}/>
        {/each}
    </div>
  <div><Platform/></div>
  
</div>

<style lang="scss">
    @import '../styles/profil.scss';
</style>