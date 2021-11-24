<script>
	import { Router, Link, Route} from "svelte-routing";
	import NavBar from "./components/Navbar.svelte";

	import Home from "./views/home.svelte";
	import Login from "./views/login.svelte";
	import Jeux from "./views/jeux.svelte";
	import Profil from "./views/profil.svelte";
	import Search from "./views/search.svelte";

    import { navigate } from "svelte-routing";
	import 'global.scss';


	let routes = ["/", "/test"]
	!routes.includes(location.pathname) && (navigate("/")); // retourne home quand modifie url 
	!sessionStorage.getItem("username") && (navigate("/login")); // retourne login quand pas connecté et modifie url

	export let url = "";
</script>

<div id="App">
	<Router {url}>
		<!-- <nav> -->
			<!-- <Link class="link" to="login">Login</Link> -->
			{#if sessionStorage.getItem("username")}
				<NavBar/>
			{/if}

		<!-- </nav> -->
		<!-- <Route path="search" component={Search} />
		<Route path="profil" component={Profil} />
		<Route path="login" component={Login} />
		<Route path="games" component={Jeux} />
		<Route path="/"><Home /></Route> -->
	</Router>
</div>

<style lang="scss">
	#App{
		display: flex;
		max-width: 1440px;
		margin: auto;
	}
</style>
