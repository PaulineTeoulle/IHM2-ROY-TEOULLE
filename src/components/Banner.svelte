<script>

import { toggleModalProfil } from "../views/profil.svelte";
export let pseudo;

</script>


<div class="Banner">
    <img src="images/kiwi.jpg" alt="ImageProfil">
    <div>
        <div class="profile">
            <img src="images/kiwi.jpg" alt="ImageProfil">
            <p>{pseudo}</p>
        </div>

        <div class="infos">
            <div class="number">129</div>
            <div class="text">Abonnements</div>
            <div class="number">8</div>
            <div class="text">Abonnés</div>
        </div>
    </div>
    <div class="editProfile">
        <img class="editIcon" src="images/svg/edit.svg" alt="edit icon"/>
        <button class="editButton" on:click={toggleModalProfil}>Editer profil</button>
    </div>
</div>

<style lang="scss">
  @import '../styles/color.scss';

  .Banner {
    background-color: $secondary;
    width: 100%;
    display: flex;
    flex-direction: column;


    & > img {
      width: 100%;
      height: 250px;
      object-fit: cover;
    }

    & > div {
      position: relative;


      & > .profile {
        position: absolute;
        top: -68px;
        left: 25px;

        & > img {
          width: 128px;
          height: 128px;
          border-radius: 50%;
          object-fit: cover;
          border: solid 4px $primary;
        }

        & p {
          margin: 0;
          text-align: center;
          font-weight: bold;
        }

      }
    }

    & > div:nth-child(2) {
      padding-top: 88px;
      display: flex;
      justify-content: flex-end;
      padding-bottom: 16px;
      margin: 0 16px;
      border-bottom: 1px solid $tertiary;
      color: $font;

    }

    & > button {
      width: fit-content;
      padding: 0 10px;
      align-self: flex-end;
      margin: 16px;
    }

    .infos {
      display: flex;
      flex-direction: row;

      .number {
        color: $font;
        margin-right: 8px;
        margin-left: 50px;
      }

      .text {
        color: $font-variation;
      }
    }

    .editProfile {
      display: flex;
      flex-direction: row;
      align-self: flex-end;
      margin: 15px;

      .editIcon {
        width: 16px;
        height: 16px;
        filter: invert(83%) sepia(2%) saturate(8%) hue-rotate(325deg) brightness(89%) contrast(94%);
      }

      .editButton {
        background-color: transparent;
        background-repeat: no-repeat;
        border: none;
        cursor: pointer;
        overflow: hidden;
        outline: none;
        text-decoration: underline;
        color: $font-variation;
      }
    }
  }

</style>
