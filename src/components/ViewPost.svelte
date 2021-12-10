<script>
    import { createEventDispatcher } from 'svelte';
    import Comment from "../components/Comment.svelte";
    import { onMount } from 'svelte';

    const dispatch = createEventDispatcher();

    function quit(){
        dispatch('quit');
    }

    let text = ''

    function addComment(){
        let newComment = [{"user" : "Pryxs","date" : "09 dec. 2021", "message" : `${text}`, "likes" : 0}]
		comments = newComment.concat(comments)
        text = ''
    }

    export let post;

    let comments = [
        {"user" : "Trucmuche", "date" : "13 nov. 2021", "message" : "Menfou t'es tellement ininteressant comme bonhomme. #PreyForSxyrp", "likes" : 13},
        {"user" : "Machinchose", "date" : "13 nov. 2021", "message" : "Trop le boss, dommage que ca fait 10ans que tout le monde a déjà fini cette quête :,))", "likes" : 21},
        {"user" : "François P.", "date" : "13 nov. 2021", "message" : "Il est mignon monsieur Pignon, il est méchant monsieur Brochant !", "likes" : 4},
        {"user" : "Pierre", "date" : "13 nov. 2021", "message" : "Celui qui dit qu'il l'a fait, je lui offre... un sandwich. - À quoi le sandwich ? - À la fraise.", "likes" : 4}
    ]



    
    function likePost(){
        let likeSvg =  document.getElementsByClassName("like")[0];
        if(likeSvg.classList.contains("filled")){
            likeSvg.setAttribute("src", "images/svg/heart.svg")
            likeSvg.classList.remove("filled")
            post.likes -= 1;
        } else {
            likeSvg.setAttribute("src", "images/svg/filled-heart.svg")
            likeSvg.classList.add("filled")
            post.likes += 1;
        }
    }


    onMount(async () => {
        let maxHeight = 0;
        let listElement = document.getElementsByClassName("hgt");
        console.log(listElement);
        [...listElement].forEach(function(element) {
            maxHeight += element.clientHeight
        });

        document.getElementsByClassName("scrollable")[0].style.height = window.innerHeight - maxHeight - 30 + "px";
	});    
</script>

<div class="View-post">
    <div>
        <p on:click={quit}>x</p>
        <img src="images/ressources/{post.image}" alt="google logo"/>
    </div>

    <div>
        <aside>
            <div class="hgt">
                <img src="images/{post.thumbnail}" alt="profil" />
                <div>
                    <span>{post.user}</span>
                    <span>{post.date}</span>
                    <p>{post.message}</p>
                </div>
            </div>


            <div class="hgt">
                <p><span>{post.likes}</span> J'aimes</p>
                <p><span>{post.comments}</span> Commentaires</p>
            </div>

            <div class="scrollable">
                {#each comments as comment}
                    <Comment comment={comment}/>
                {/each} 
            </div>

            <div class="hgt">
                <input type="text" bind:value={text} placeholder="commentez..." />
                <button on:click={addComment}><img src="images/svg/send.svg" alt="icon envoyer"></button>
            </div>
        </aside>
    </div>
</div>

<style lang="scss">
    @import '../styles/color.scss';

    .View-post{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 10;
        display: flex;


        &>div:first-child{
            width: 70%;
            display: flex;
            align-items: center;
            justify-content: center;

            &>p:first-child{
                position: absolute;
                top: 10px;
                left: 10px;
                z-index: 20;
                background-color: $secondary;
                border-radius: 50%;
                margin: 0;
                color: $font;
                font-size: 28px;
                text-align: center;
                width: 48px;
                height: 48px;
                cursor: pointer;
            }
            &>img{
                width: auto;
                max-width: 100%;
                max-height: 80vh;
            }
        }

        &>div:nth-child(2){
            background-color: $secondary;
            color: $font;
            width: 30%;
            min-width: 300px;


            &>aside{
                position: relative;
                height: 100%;

                &>div:first-child{
                    padding: 16px;
                    display: flex;

                    &>img{
                        width: 32px;
                        height: 32px;
                        border-radius: 50%;
                        object-fit: cover;
                    }

                    &>div{
                        margin-left: 8px;
                        width: 80%;

                        &>span:first-child{
                            font-weight: bold;
                        }

                        &>span:nth-child(2){
                            margin-left: 16px;
                            color: $font-variation;
                        }
                    }
                }

                &>div:nth-child(2){
                    padding: 16px 0px;
                    margin: 0 16px;
                    border-top: 1px solid $tertiary;
                    border-bottom: 1px solid $tertiary;
                    display: flex;
                    justify-content: space-around;
                    font-size: 16px;

                    &>p>span{
                        font-weight: bold;
                    }

                    &>p{
                        margin: 0;
                    }
                }

                &>div:nth-child(3){
                    padding: 16px;
                    overflow-y: scroll;

                    &::-webkit-scrollbar{
                        display: none;
                    }
                }

                &>div:nth-child(4){
                    box-shadow: 0px -8px 14px 5px $secondary;
                    z-index: 30;
                    background-color: $secondary;
                    position: absolute;
                    bottom: 0;
                    width: 100%;
                    display: flex;
                    justify-content: space-between;
                    align-items: center;
                    margin: 0 16px 8px 16px;
                    padding: 16px 0px 8px 0px;
                    border-top: 1px solid $tertiary;
                    width: -webkit-fill-available;

                    &>input{
                        height: 32px;
                        background-color: $tertiary;
                        border-radius: 5px;
                        border: none;
                        outline: none;
                        color: $font;
                        width: -webkit-fill-available;
                        padding-left: 8px;
                    }

                    &>button{
                        background-color: transparent;
                        border: none;
                        outline: none;
                        margin-left: 16px;
                        margin-right: 8px;

                        &>img{
                            height: 32px
                        }
                    }
                }

            }
        }
    }
</style>
