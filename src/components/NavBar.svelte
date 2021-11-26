<script>
    import { Router, Link, Route} from "svelte-routing";
    import { toggleModal } from "../views/home.svelte";
    import { onMount } from 'svelte';


    onMount(async () => {
        let path = document.location.pathname;
        let bodyList = document.querySelector("body")

        let observer = new MutationObserver(function(mutations) {
            mutations.forEach(function(mutation) {
                if (path != document.location.pathname) {
                    path = document.location.pathname;
                    activatePath(path)
                }
            });
        });
        
        let config = {
            childList: true,
            subtree: true
        };
        
        observer.observe(bodyList, config);
    });

    function activatePath(path){
        let links = document.getElementsByClassName("navBarLink")
        for (let link of links) {
            console.log(link)
        }
        // path = path == "/" ? "home" : path.slice(1); 
        // console.log(path) 
        // let links = document.getElementsByClassName("navBarLink")
        // for (let link of links) {
        //     for (let classe of link.classList) {
        //         if(classe == "active"){
        //             link.classList.toggle("active")
        //         }
        //         if(classe == path){
        //             link.classList.toggle("active")
        //         }
        //     }
        // }
    }
</script>

<nav>
    <img id="logo" src="images/HerobrineLogo.svg" alt="logo Herobrine"/>

    <Link to="/" class="navBarLink home active">
        <img src="images/svg/accueil.svg" alt="accueil icon" />
        Accueil
    </Link>
	<Link to="games" class="navBarLink games">
        <img src="images/svg/game-controller.svg" alt="jeux icon" />
        Jeux
    </Link>
    <Link to="search" class="navBarLink search">
        <img src="images/svg/group.svg" alt="recherche icon" />
        Recherche
    </Link>
	<Link to="profil" class="navBarLink profil">
        <img id="profil" src="images/svg/loupe.svg" alt="profil icon" />
        Profil
    </Link>

    <button on:click={toggleModal}> Poster </button>
</nav>

<style lang="scss">
        @import '../styles/navbar.scss';

</style>
