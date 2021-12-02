<script>
	 let platformInfos = [
		{"platforme" : "Skype", "pseudo" : "ipryx", "thumbnail": "skype.png"},
		{"platforme" : "Discord", "pseudo" : "pryxs#6784", "thumbnail": "discord.png"},
		{"platforme" : "Steam" , "pseudo" :"zPryxs", "thumbnail": "steam.png"},
		{"platforme" : "Twitch" , "pseudo" : "Pryxs", "thumbnail": "twitch.png"}
	]

</script>


<div class="Platform">
 Autres plateformes

 {#each platformInfos as platform}

 <div><img src="images/{platform.thumbnail}" alt="profil" />{platform.platforme} : {platform.pseudo}</div>
    
{/each}

</div>
<style lang="scss">
	@import '../styles/color.scss';

    .Platform{
        background-color: $tertiary;
        width: 100%;
        margin: 0 24px;
        color: $dynamic;
        margin-left: 30px;
        margin-right: 20px;
        img{
            width: 25px;
            height: auto;
        }
    }
	
</style>
