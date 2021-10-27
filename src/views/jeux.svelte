<script>
    export let location;
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
        { name: 'Black Ops - Cold War', posts: '88K', thumbnail: '' ,fav: false},
        { name: 'Little Nightmares', posts: '5679', thumbnail: '',fav: false },
        { name: 'Inside', posts: '9879', thumbnail: '',fav: false },
        { name: 'Anno 1404', posts: '2342', thumbnail: '',fav: false },
	];
</script>

<div class="Jeux">
    <div>
        <h2>Jeux</h2>
        <input type='text' placeholder="Rechercher un jeu"/>
    </div>

    <ul>
        {#each jeux as jeu}
            <li>
                <Jeu jeu={jeu}/>
            </li>
        {/each}
    </ul>
</div>

<style lang="scss">
    @import '../styles/jeux.scss';
</style>