<script>
    import Redirect from "./Redirect.svelte";

    export let location;
</script>

{#if localStorage.getItem("username")}
    <slot {...$$restProps} />
{:else}
    <Redirect to="/login" state={{ from: location }} />
{/if}
