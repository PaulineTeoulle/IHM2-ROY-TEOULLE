<script>
    export let comment;
</script>

<div class="Comment">
    <div>
        <img src="images/svg/user.svg" alt="icon user">
    </div>
    <div>
        <p>{comment.user} <span>{comment.date}</span></p>
        <p>{comment.message}</p>
        <p><img src="images/svg/heart.svg" alt="like icon" /> {comment.likes}</p>
    </div>
</div>

<style lang="scss">
    @import '../styles/color.scss';

    .Comment{
        display: flex;
        justify-content: flex-start;
        margin-bottom: 16px;

        &>div:first-child{
            margin-right: 16px;
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background-color: $tertiary;
            display: flex;
            align-items: center;
            justify-content: center;

            &>img{
                height: 60%;
                width: auto;
            }
        }

        &>div:nth-child(2){
            width: 85%;

            &>p{
                margin: 0;
                margin-bottom: 8px;
            }

            &>p:first-child{
                font-weight: bold;

                &>span{
                    color: $font-variation;
                    font-weight: normal;
                    margin-left: 8px;
                }
            }

            &>p:last-child{
                display: flex;
                align-items: center;
                font-size: 12px;

                &>img{
                    height: 16px;
                    width: auto;
                    margin-right: 8px;
                }
            }
        }
    }

</style>