<script>
    import Jeu from "../components/Jeu.svelte";

    let jeux = [
		{ name: 'League of Legends', posts: '79K', thumbnail: 'lol.jpg', fav: true },
        { name: 'Dofus', posts: '8 678', thumbnail: 'dofus.jpg', fav: true },
        { name: 'Fortnite', posts: '234K', thumbnail: 'fortnite.jpg', fav: false },
        { name: 'Grand Theft Auto V', posts: '187K', thumbnail: 'GTA.jpeg',fav: false },
        { name: 'DOOM', posts: '32K', thumbnail: 'DOOM.jpg',fav: false },
        { name: 'New World', posts: '14K', thumbnail: 'NW.jpg',fav: true },
        { name: 'Minecraft', posts: '54K', thumbnail: 'minecraft.jpg',fav: false },
        { name: 'Apex Legends', posts: '22K', thumbnail: 'apex.jpg', fav: true },
        { name: 'Black Ops - Cold War', posts: '88K', thumbnail: 'coldWar.jpg' ,fav: false},
        { name: 'Little Nightmares', posts: '5679', thumbnail: 'LN.jpg',fav: false },
        { name: 'Inside', posts: '9879', thumbnail: 'inside.jpg',fav: false },
        { name: 'Les Sims 4', posts: '2342', thumbnail: 'sims.jpg',fav: false },
        { name: 'Animal Crossing', posts: '2342', thumbnail: 'animalCrossing.jpg',fav: false },
        { name: 'Zelda', posts: '2342', thumbnail: 'zelda.jpg',fav: false },
        { name: 'Anno 1404', posts: '2342', thumbnail: 'anno.jpg',fav: false },
	];

    function toggleFav(jeu){
        let newJeu = jeu.detail;
        newJeu.fav = newJeu.fav ? false : true;
        jeux[jeux.indexOf(jeu.detail)] = newJeu
    }


</script>

<div class="Jeux">
    <div>
        <h2>Jeux</h2>
        <input type='text' placeholder="Rechercher un jeu"/>
    </div>

    <ul>
        {#each jeux as jeu}
            <li>
                <Jeu jeu={jeu} on:toggleFav={toggleFav}/>
            </li>
        {/each}
    </ul>
</div>

<style lang="scss">
    @import '../styles/jeux.scss';
</style>