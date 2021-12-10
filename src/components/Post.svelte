<script>
    import ViewPost from "../components/ViewPost.svelte";
    import { createEventDispatcher } from 'svelte';

    export let post;

    let show = false;

    function showPost(){
        let bg = document.getElementsByClassName("background")[0]
        bg.style.display = "block";
        show = true;
    }

    function quit(){
        let bg = document.getElementsByClassName("background")[0]
        bg.style.display = "none";
        show = false;
    }


    function likePost(event){
        let likeSvg =  event.target;
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

</script>

{#if show}
    <ViewPost post={post} on:quit={quit}/>
{/if}

<div class="Post">
    <div on:click={showPost}>
        <img src="images/{post.thumbnail}" alt="profil" />
        <div>
            <span>{post.user}</span>
            <span>@{post.game}</span>
            <p>{post.message}</p>
        </div>
    </div>
    <img on:click={showPost} src="images/ressources/{post.image}" alt="google logo"/>
    <div class="post-footer">
        <div>
            <span><img on:click={likePost} src="images/svg/heart.svg" alt="like icon" class="like"/> {post.likes}</span>
            <span><img on:click={showPost} src="images/svg/comment.svg" alt="comment icon" /> {post.comments}</span>
        </div>
        <span>{post.date}</span>
    </div>
</div>

<style lang="scss">
    @import '../styles/post.scss';
</style>
