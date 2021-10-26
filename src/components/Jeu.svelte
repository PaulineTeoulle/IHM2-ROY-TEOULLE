<script>
    export let jeu;

</script>

<div class="Jeu">
    <!-- {#if jeu.thumbnail}
        <img src="images/thumbnails/{jeu.thumbnail}" alt="vignette du jeu {jeu.name}"/>
    {:else} -->
        <img src="images/background.png" alt="vignette par défaut"/>
    <!-- {/if} -->
    <h3>{jeu.name}</h3>
    <p>{jeu.posts} postes</p>
    <button>ajouter en favoris</button>
</div>

<style lang="scss">
    @import '../styles/jeu.scss';
</style>