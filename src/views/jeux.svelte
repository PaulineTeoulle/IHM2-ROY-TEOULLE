<script>
    export let location;
    import Jeu from "../components/Jeu.svelte";

    let jeux = [
		{ name: 'League of Legends', posts: '79K', thumbnail: 'lol.jpg' },
        { name: 'Dofus', posts: '8 678', thumbnail: 'dofus.jpg' },
        { name: 'Fortnite', posts: '234K', thumbnail: 'fortnite.jpg' },
        { name: 'Grand Theft Auto V', posts: '187K', thumbnail: 'GTA.jpeg' },
        { name: 'DOOM', posts: '32K', thumbnail: 'DOOM.jpg' },
        { name: 'New World', posts: '14K', thumbnail: 'NW.jpg' },
        { name: 'Minecraft', posts: '54K', thumbnail: 'minecraft.jpg' },
        { name: 'Apex Legends', posts: '22K', thumbnail: 'apex.jpg' },
        { name: 'Black Ops - Cold War', posts: '88K', thumbnail: '' },
        { name: 'Little Nightmares', posts: '5679', thumbnail: '' },
        { name: 'Inside', posts: '9879', thumbnail: '' },
        { name: 'Anno 1404', posts: '2342', thumbnail: '' },
	];
</script>

<div class="Jeux">
    <div>
        <h2>Jeux</h2>
        <input type='text' />
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