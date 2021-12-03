<script>
    import Banner from "../components/Banner.svelte";
    import Post from "../components/Post.svelte";
    import Platform from "../components/Platform.svelte";

    let posts = [
        {
            "user": "Sxyrp",
            "thumbnail": "kiwi.jpg",
            "game": "Dofus",
            "message": "Quête tutu presque terminée !!! Demain gros rush temporis (bougle dj gelé pour drop le gelano) :p",
            "image": "tutu.png",
            "comments": "13",
            "likes": 70,
            "date": "13 nov. 2021"
        },
        {
            "user": "Sxyrp",
            "thumbnail": "kiwi.jpg",
            "game": "Dofus",
            "message": "Super le donjon avec les potes",
            "image": "caverne.png",
            "comments": "8",
            "likes": 53,
            "date": "12 nov. 2021"
        }
    ]
</script>
<main>
    <div id="Profil">
        <div class="MidContainer">
            <Banner/>
            {#each posts as post}
                <Post post={post}/>
            {/each}
        </div>
        <div id="RigthBar"><Platform/></div >
    </div>
</main>

<style lang="scss">
  @import '../styles/profil.scss';
  @import '../styles/rightbar.scss';
</style>