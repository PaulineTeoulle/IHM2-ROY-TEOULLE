<script>
    import { toggleModalProfil } from "../views/profil.svelte";
    import { createEventDispatcher } from 'svelte';

    export let pseudo;
    export let platformInfos 
  
    const dispatch = createEventDispatcher();

    function editName(){
        dispatch('message', {
          tableau :  platformInfos
        });
        toggleModalProfil();
    }

</script>

<div class="ModalProfil">
    <div>
        <img src="images/kiwi.jpg" alt="profil" />
        <span>{pseudo}</span>
    </div>

    <div>
        <div>
            <div class="text">Pseudo</div>
            <input type="text" bind:value={pseudo}/>
        </div>

        <div>
        <div>
            <div>
                <div  class="text">{platformInfos[0]['platforme']}</div>
                <input type="text" bind:value={platformInfos[0]['pseudo']}/>
            </div>
            <div>
                <div  class="text">{platformInfos[1]['platforme']}</div>
                <input type="text" bind:value={platformInfos[1]['pseudo']}/>
            </div>
            <div>
                <div  class="text">{platformInfos[2]['platforme']}</div>
                <input type="text" bind:value={platformInfos[2]['pseudo']}/>
            </div>
        </div>
       
        <div>
            <div> 
                <div  class="text">{platformInfos[3]['platforme']}</div></div>
                <input type="text" bind:value={platformInfos[3]['pseudo']}/>
            <div> 
                <div  class="text">{platformInfos[4]['platforme']}</div>
                <input type="text" bind:value={platformInfos[4]['pseudo']}/>
            </div>
            <div>
                <div  class="text">{platformInfos[5]['platforme']}</div>
                <input type="text" bind:value={platformInfos[5]['pseudo']}/>
            </div>

        </div>
        </div>
    </div>
    
    <div>
        <button on:click={editName}>Sauvegarder</button>
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
        width: 40%;
        min-width: 400px;
        border-radius: 10px;


        .text{

            color: $font-variation;
        }
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
            &>div:nth-child(2){
                display: flex;
                &>div:first-child{
                    width: 50%;
                    margin-right: 8px;
                }

                &>div:nth-child(2){
                    width: 50%;
                    margin-left: 8px;
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

        input{
            padding: 5px;
            font-family: sans-serif;
            height: 2.5em;
            width: -webkit-fill-available;;
            border: none;
            background-color: $tertiary;
            border-radius: 5px;
            color: $font;
            margin-bottom: 16px;

            &:focus{
                outline: none;
            }
        }
    }
</style>