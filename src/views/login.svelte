<script>
    import { onMount } from "svelte";
    export let location;

    let users = {username : "toto", password : "mdp"};
    let username, password; 

    const SignIn = () => {
        console.log(username, password)
        if(users.username === username && users.password === password){
            localStorage.setItem("username", username);
        } else {
            alert("pas bon")
        }
    }

    // set image movible
    onMount(() => {
        const switchDiv = document.getElementsByClassName("switch-side");
        switchDiv[0].style.backgroundImage  = "url(images/background.png)";
    });

    // elements animés
    const switchDiv = document.getElementsByClassName("switch-side");
    const buttonGoToSignUp = document.getElementsByClassName("goToSignUp");
    const buttonGoToSignIn = document.getElementsByClassName("goToSignIn");
    const forms = document.getElementsByTagName("form");

    // animations gauche
    const goToSignUp = () => {
        forms[0].style.opacity = 0;
        forms[1].style.opacity = 1;
        switchDiv[0].style.transform = "translate(-50%)";
        switchDiv[0].style.backgroundPositionX = "left";
        buttonGoToSignUp[0].style.display = "none";
        buttonGoToSignIn[0].style.display = "initial";
    }

    // animations droite
    const goToSignIn = () => {
        forms[0].style.opacity = 1;
        forms[1].style.opacity = 0;
        switchDiv[0].style.transform = "translate(50%)";
        switchDiv[0].style.backgroundPositionX = "right";
        buttonGoToSignIn[0].style.display = "none";
        buttonGoToSignUp[0].style.display = "initial";
    }
</script>

<div class="Login">
    <main>
        <form>
            <h3>S'identifier</h3>
            <button class="google-connect">
                <img src="images/svg/google.png" alt="google logo"/>
                Se connecter avec Google
            </button>
            <label for="username">Nom d'utilisateur</label>
            <input id="username" placeholder="Ex : Tartempion27" type="text" bind:value={username}/>
            <label for="password">Mot de passe</label>
            <input id="password" type="text" bind:value={password}/>
            <button class="primary-action" on:click={SignIn}>Connexion</button>
        </form>


        <form>
            <h3>Créer votre compte</h3>
            <label for="username">Nom d'utilisateur</label>
            <input id="username" placeholder="Ex : Tartempion27"/>
            <label for="mail">Mail</label>
            <input id="mail" placeholder="Ex : Tartempion@gmail.com"/>
            <label for="password">Mot de passe</label>
            <input id="password"/>
            <label for="password">Confirmation mot de passe</label>
            <input id="password"/>
            <button class="primary-action" on:click={SignIn}>S'inscrire</button>
        </form>
        <div class="switch-side right-side">
            <div>
                <img src="images/HerobrineLogo.svg" alt="logo Herobrine"/>
                <button class="goToSignUp" on:click={goToSignUp}>Créer un compte</button>
                <button class="goToSignIn" on:click={goToSignIn}>Se connecter</button>
            </div>
        </div>
    </main>
</div>

<style lang="scss">
    @import '../styles/login.scss';
</style>