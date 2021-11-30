<script>
    import { Router, Link, Route} from "svelte-routing";
    import { toggleModal } from "../views/home.svelte";
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
    <Link to="chat" class="navBarLink chat">
        <img src="images/svg/group.svg" alt="recherche icon" />
        Discussion
    </Link>
	<Link to="profil" class="navBarLink profil">
        <img class="profil-image" src="images/kiwi.jpg" alt="profil" />
        Profil
    </Link>

    <button on:click={toggleModal}> Poster </button>
</nav>

<style lang="scss">
        @import '../styles/navbar.scss';

</style>
