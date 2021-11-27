<script>
    import { toggleModal } from "../views/home.svelte";
    import { createEventDispatcher } from 'svelte';

    let text = ""

    const dispatch = createEventDispatcher();

    function post(){
        dispatch('message', {
            text: text
        });
        toggleModal();
    }

</script>

<div class="Modal">
    <div>
        <img src="images/kiwi.jpg" alt="profil" />
        <span>Pryxs</span>
    </div>

    <textarea maxlength="255" bind:value={text}></textarea>

    <div>
        <div>
            <button>+</button><span>Ajouter un média</span>
        </div>
        <select>
            <option value="" selected disabled>Sélectionner un jeu</option>
            <option value="">Dofus</option>
            <option value="">Rocket League</option>
        </select>
    </div>

    <div>
        <button on:click={post}>Poster</button>
        <button on:click={toggleModal}>Annuler</button>
    </div>
</div>

<style lang="scss">
    @import '../styles/color.scss';

    .Modal{
        z-index: 1;
        background-color: $primary;
        display: none;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        padding: 24px;
        width: 30%;
        min-width: 350px;
        border-radius: 10px;

        &>div:first-child{
            margin: 0 0 16px 0;
            color: $font;
            display: flex;
            align-items: center;

            &>img{
                border-radius: 50%;
                object-fit: cover;
                width: 40px;
                height: 40px;
                margin-right: 16px;
            }

            &>span{
                font-weight: bold;
            }
        }
        
        textarea{
            padding: 5px;
            font-family: sans-serif;
            height: 8em;
            width: 100%;
            border: none;
            background-color: $tertiary;
            border-radius: 5px;
            color: $font;
            margin-bottom: 16px;

            &:focus{
                outline: none;
            }
        }

        &>div:nth-child(3){
            display: flex;
            justify-content: space-between;
            margin-bottom: 16px;

            &>div{
                &>button{
                    background-color: transparent;
                    border: 1px solid $tertiary;
                    border-radius: 5px;
                    color: $font;
                    padding: 10px 20px;
                    outline: none;
                }

                &>span{
                    margin-left: 16px;
                    color: $font-variation;
                }
            }

            &>select{
                background-color: $tertiary;
                border: none;
                border-radius: 5px;
                padding: 5px 15px;
                color: $font-variation;
                outline: none;
            }
        }

        &>div:nth-child(4){
            display: flex;
            button{
                margin-top: 24px;
                font-size: 1.2em;
                color: white;
                width: 100%;
                border-radius: 10px;
                border: none;
                padding: 10px 50px 10px 50px;
            }

            &>button:first-child{
                background-color: #03dac5;
                margin-right: 10px;
            }

            &>button:nth-child(2){
                background-color: transparent;
                margin-left: 10px;
                border: 2px solid $tertiary;
                color: $font-variation;
            }
        }
    }
</style>