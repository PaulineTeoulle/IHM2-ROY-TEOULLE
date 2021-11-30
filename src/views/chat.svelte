<script>
    import { onMount } from 'svelte';

    let messages = [
        {"user" : 0, "message" : "Celui qui dit qu'il l'a tué, je lui offre... un sandwich"},
        {"user" : 1, "message" : "Chef chef, a quoi le sandwich ? "},
        {"user" : 0, "message" : "Un sandwich… a la fraise !"}
    ]

    let message = ""

    function sendMessage(){

    }

    onMount(async () => {
        let maxHeight = 0;
        let listElement = document.getElementsByClassName("hgt");
        console.log(listElement);
        [...listElement].forEach(function(element) {
            maxHeight += element.clientHeight
        });
        let containerHeight = document.getElementsByClassName("Chat")[0].clientHeight;
        console.log(containerHeight)
        console.log(maxHeight)
        document.getElementsByClassName("conversation")[0].style.height = containerHeight - maxHeight - 90 + "px";
	});    
</script>

<div class="Chat">
    <div>
        <div class="hgt">
            <div>
                <img class="profil-image" src="images/kiwi.jpg" alt="profil" />
                <span></span>
            </div>
            <div>
                <p>Ravio'league</p>
                <span>en ligne</span>
            </div>
        </div>

        <div class="conversation">
            <span>Aujourd'hui</span>
            {#each messages as message}
                <div class="{message.user === 0 ? 'guest' : 'host'}">
                    {#if message.user === 0}
                        <img src="images/kiwi.jpg" alt="profil" />
                    {/if}
                    <p>{message.message}</p>
                </div>
            {/each}
        </div>

        <div class="hgt">
            <img src="images/svg/img.svg" alt="add img"/>
            <img src="images/svg/gif.svg" alt="add gif"/>
            <input type="text" bind:value={message} placeholder="Aa"/>
            <button on:click={sendMessage}><img src="images/svg/send.svg" alt="icon envoyer"></button>
        </div>
    </div>

    <div>

    </div>
</div>

<style lang="scss">
    @import "../styles/color.scss";

    .Chat{
        display: flex;
        height: 93%;
        width: 100%;
        margin: 24px 24px 24px 0;

        &>div:first-child{
            width: 65%;
            background: $secondary;
            margin-right: 24px;

            &>div:first-child{
                display: flex;
                padding: 16px;
                height: fit-content;

                &>div:first-child{
                    position: relative;
                    &>img{
                        width: 40px;
                        height: 40px;
                        border-radius: 50%;
                        object-fit: cover;
                    }
                    &>span{
                        position: absolute;
                        top: 28px;
                        left: 28px;
                        width: 8px;
                        height: 8px;
                        border: 2px solid $secondary;
                        background: green;
                        border-radius: 50%;
                    }
                }
                &>div:nth-child(2){
                    width: 100%;
                    margin-left: 16px; 

                    &>p{
                        color: $font;
                        font-weight: bold;
                        margin: 0;
                        font-size: 16px;
                    }

                    &>span{
                        color: $font-variation;
                        font-size: 14px;
                    }
                }
            }

            &>div:nth-child(2){
                background-color: $primary;
                margin: 16px;
                border-radius: 5px;
                display: flex;
                flex-direction: column;
                justify-content: flex-end;
                padding-bottom: 32px;

                &>span{
                    color: $font-variation;
                    font-weight: bold;
                    font-size: 12px;
                    align-self: center;
                    margin-bottom: 16px;
                }

                &>div{
                    display: flex;
                    align-items: center;

                    &>p{
                        margin: 8px 0;
                        border-radius: 8px;
                        color: $font;
                        width: fit-content;
                        padding: 8px 16px;
                    }

                    &>img{
                        height: 24px;
                        width: 24px;
                        object-fit: cover;
                        border-radius: 50%;
                        margin-right: 16px;
                    }
                }

                &>.host{
                    align-self: flex-end;
                    margin-right: 16px;

                    &>p{
                        background-color: $dynamic;
                    }
                }

                &>.guest{
                    align-self: flex-start;
                    margin-left: 16px;
                    &>p{
                        background-color: $secondary;
                    }
                }
            }

            &>div:nth-child(3){
                display: flex;
                margin: 16px;
                align-items: center;
                margin-top: 24px;
                
                &>img{
                    width: 24px;
                    height: 24px;
                    margin-right: 24px;
                }

                &>input{
                    width: 100%;
                    border: none;
                    border-radius: 5px;
                    background-color: $tertiary;
                    color: $font;
                    margin-right: 24px;
                    height: 2.5em;
                    font-size: 18px;
                    padding-left: 16px;
                }

                &>button{
                    background-color: transparent;
                    border: none;
                    outline: none;
                }
            }
        }

        &>div:nth-child(2){
            width: 35%;
            min-width: 250px;
            background: green;
        }
    }
</style>