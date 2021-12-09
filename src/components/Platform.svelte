<script>
  export let platformInfos;
</script>

<div id="Platform">
    <h3 class="title">Autres plateformes</h3>
    <div class="list">
        {#each platformInfos as platform}
        {#if platform.pseudo}
            <div class="platform">
                <img src="images/{platform.thumbnail}" alt="profil"/>
                <div class="name">{platform.platforme} : </div>
                <div class="pseudo">{platform.pseudo}</div>
            </div>
          {/if}
        {/each}
    </div>
</div>

<style lang="scss">
  @import '../styles/color.scss';

  #Platform {
    background-color: $tertiary;
    border-radius: 10px;
    margin: 0 0 0 30px;

    img {
      width: 25px;
      height: auto;
      margin-right: 16px;
    }

    .title {
      color: $font;
      padding-top: 20px;
      font-weight: bold;
      margin: 0 0 0 24px;
    }

    .list {
      color: $font;
      margin-left: 10px;
      padding-bottom: 30px;
    }

    .platform {
      display: flex;
      flex-direction: row;
        margin-top: 16px;
        margin-left: 16px;
      .name {
        color: $font-variation;
        margin-right: 8px;
      }

      .pseudo {
        color: $font;
      }
    }
  }


</style>
