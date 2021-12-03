<script>
    let platformInfos = [
        {"platforme": "Skype", "pseudo": "ipryx", "thumbnail": "skype.png"},
        {"platforme": "Discord", "pseudo": "pryxs#6784", "thumbnail": "discord.png"},
        {"platforme": "Steam", "pseudo": "zPryxs", "thumbnail": "steam.png"},
        {"platforme": "Twitch", "pseudo": "Pryxs", "thumbnail": "twitch.png"}
    ]

</script>


<div class="Platform">
 <h3 id="title">Autres plateformes</h3>
    <div id="liste">
    {#each platformInfos as platform}

        <div><img src="images/{platform.thumbnail}" alt="profil"/>{platform.platforme} : {platform.pseudo}</div>

    {/each}
    </div>

</div>
<style lang="scss">
  @import '../styles/color.scss';

  .Platform {


    background-color: $tertiary;
    width: 100%;
    color: $dynamic;
    border-radius: 10px;
    margin: 0 20px 0 30px;

    img {
      width: 25px;
      height: auto;
    }

   #title {
    color: $font;
    margin-left: 20px;
    padding-top: 20px;
    font-weight: bold;
   }

   #liste {
    color: $font;
    margin-left: 10px;
    padding-bottom: 30px;
   }
  }


</style>
