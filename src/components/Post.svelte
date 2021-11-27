<script>
    import ViewPost from "../components/ViewPost.svelte";

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
            <span><img src="images/svg/heart.svg" alt="like icon" /> {post.likes}</span>
            <span><img src="images/svg/comment.svg" alt="comment icon" /> {post.comments}</span>
        </div>
        <span>{post.date}</span>
    </div>
</div>

<style lang="scss">
    @import '../styles/post.scss';
</style>
