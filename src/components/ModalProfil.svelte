<script>
    import { toggleModalProfil } from "../views/profil.svelte";
    import { createEventDispatcher } from 'svelte';

    let text = ""

    const dispatch = createEventDispatcher();

    function post(){
        dispatch('message', {
            text: text
        });
        toggleModalProfil();
    }

</script>

<div class="ModalProfil">
    <div>
        <img src="images/kiwi.jpg" alt="profil" />
        <span>Pryxs</span>
    </div>

    <div>
        <div>
            <div>Pseudo</div>
            <input type="text" bind:value={text}/>
        </div>

        <div>
        <div>
            <div>
                <div>Skype</div>
                <input type="text" bind:value={text}/>
            </div>
            <div>
                <div>Steam</div>
                <input type="text" bind:value={text}/>
            </div>
            <div>
                <div>Ubisoft</div>
                <input type="text" bind:value={text}/>
            </div>
        </div>
       
        <div>
            <div> 
                <div>Discord</div></div>
                <input type="text" bind:value={text}/>
            <div> 
                <div>Epic Games</div>
                <input type="text" bind:value={text}/>
            </div>
            <div>
                <div>Twitch</div>
                <input type="text" bind:value={text}/>
            </div>

        </div>
        </div>
    </div>
    
    <div>
        <button on:click={post}>Sauvegarder</button>
        <button on:click={toggleModalProfil}>Annuler</button>
    </div>
</div>

<style lang="scss">
    @import '../styles/color.scss';

    .ModalProfil{
        z-index: 10;
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

        &>div:nth-child(2){
            background-color: red;

         

            &>div:nth-child(2){
                display: flex;

                
                &>div:first-child{
                    width: 50%;
                    background-color: yellow;
                }

                &>div:nth-child(2){
                    width: 50%;
                    background-color: green;
                }
               
            }
        }
    
       
        &>div:nth-child(3){
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