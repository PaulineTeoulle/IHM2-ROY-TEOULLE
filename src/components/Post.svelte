<script>
    export let post;
</script>

<div class="Post">
    <div>
        <img src="images/{post.thumbnail}" alt="profil" />
        <div>
            <span>{post.user}</span>
            <span>@{post.game}</span>
            <p>{post.message}</p>
        </div>
    </div>
    <img src="images/ressources/{post.image}" alt="google logo"/>
</div>

<style lang="scss">
    @import '../styles/post.scss';
</style>
