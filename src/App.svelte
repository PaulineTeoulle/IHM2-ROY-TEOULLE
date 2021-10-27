<script>
	import { Router, Link, Route} from "svelte-routing";
	import Home from "./views/home.svelte";
	import Login from "./views/login.svelte";
	import Jeux from "./views/jeux.svelte";
    import { navigate } from "svelte-routing";
	import 'global.scss';


	let routes = ["/", "/test"]
	!routes.includes(location.pathname) && (navigate("/")); // retourne home quand modifie url 
	!sessionStorage.getItem("username") && (navigate("/login")); // retourne login quand pas connecté et modifie url

	export let url = "";
</script>

<div id="App">
	<Router {url}>
		<nav>
			<!-- <Link class="link" to="login">Login</Link> -->
			{#if sessionStorage.getItem("username")}
				<Link to="/">Home</Link>
				<Link to="jeux">Jeux</Link>
			{/if}

		</nav>
		<Route path="login" component={Login} />
		<Route path="jeux" component={Jeux} />
		<Route path="/"><Home /></Route>
	</Router>
</div>

<style lang="scss">
	#App{
		display: flex;
		max-width: 1440px;
		margin: auto;

		nav{
			min-width: 200px;
			background-color: grey;
			margin-right: 32px;
		}
	}
</style>
