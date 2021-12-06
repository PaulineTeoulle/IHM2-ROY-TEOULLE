<script>
    import Banner from "../components/Banner.svelte";
    import Post from "../components/Post.svelte";
    import Platform from "../components/Platform.svelte";
    
    import ModalProfile from "../components/ModalProfil.svelte";

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


<script context="module">
    export function toggleModalProfil(){
        let modal = document.getElementsByClassName("ModalProfil")[0]
        let bg = document.getElementsByClassName("background")[0]
        let style = getComputedStyle(modal).display;

        switch(style){
            case "none":
                modal.style.display = "block";
                bg.style.display = "block";
                break;
            case "block":
                modal.style.display = "none";
                bg.style.display = "none";
                break;
            default:
                break;
        }
    }
</script>

<div id="Profil">
    <div class="MidContainer">
        <Banner/>
        {#each posts as post}
            <Post post={post}/>
        {/each}
    </div>
    <div id="RigthBar">
        <Platform/>
    </div>    

    <ModalProfile/>
	<div class="background"></div>

</div>


<style lang="scss">
  @import '../styles/profil.scss';
  @import '../styles/rightbar.scss';

  .background{
			filter: contrast(.4);
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
</style>