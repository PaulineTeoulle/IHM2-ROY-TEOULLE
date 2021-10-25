<script>
	import { Router, Link, Route} from "svelte-routing";
	import Home from "./views/home.svelte";
	import Login from "./views/login.svelte";
	import Test from "./views/test.svelte";
    import { navigate } from "svelte-routing";
	import 'global.scss';


	let routes = ["/", "/test"]
	!routes.includes(location.pathname) && (navigate("/")); // retourne home quand modifie url 
	!localStorage.getItem("username") && (navigate("/login")); // retourne login quand pas connecté et modifie url

	export let url = "";
</script>

<Router {url}>
	<nav>
		<!-- <Link class="link" to="login">Login</Link> -->
		{#if localStorage.getItem("username")}
			<Link to="/">Home</Link>
			<Link to="test">Test</Link>
		{/if}

	</nav>
	<div>
		<Route path="login" component={Login} />
		<Route path="test" component={Test} />
		<Route path="/"><Home /></Route>
	</div>
</Router>

<style text="text/scss">

</style>
