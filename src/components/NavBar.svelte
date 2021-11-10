<script>
    import { Router, Link, Route} from "svelte-routing";
    export let navbar;
</script>


<nav>
    <img id="logo" src="images/HerobrineLogo.svg" alt="logo Herobrine"/>

    <Link to="/" class="navBarLink">
        <img src="images/svg/accueil.svg" alt="accueil icon" />
        Accueil
    </Link>
	<Link to="games">
        <img src="images/svg/game-controller.svg" alt="jeux icon" />
        Jeux
    </Link>
    <Link to="search">
        <img src="images/svg/group.svg" alt="recherche icon" />
        Recherche
    </Link>
	<Link to="profil">
        <img id="profil" src="images/svg/loupe.svg" alt="profil icon" />
        Profil
    </Link>

    <button> Poster </button>
</nav>

<style lang="scss">
    @import '../styles/navbar.scss';

</style>
