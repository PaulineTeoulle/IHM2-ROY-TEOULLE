<script>
    export let jeu;
</script>

<div class="Jeu">
    {#if jeu.thumbnail}
        <img src="images/thumbnails/{jeu.thumbnail}" alt="vignette du jeu {jeu.name}"/>
    {:else}
        <img src="images/thumbnails/default.png" alt="vignette par défaut"/>
    {/if}

    <h3>{jeu.name}</h3>
    <p>{jeu.posts} postes</p>

    {#if jeu.fav}
        <button class="remove-fav">enlever des favoris</button>
    {:else}
        <button class="add-fav">ajouter en favoris</button>
    {/if}

    {#if jeu.fav}
        <img class="favoris" src="images/svg/fav.svg" alt="jeu {jeu.name} est en favoris" />
    {/if}
</div>

<style lang="scss">
    @import '../styles/jeu.scss';
</style>