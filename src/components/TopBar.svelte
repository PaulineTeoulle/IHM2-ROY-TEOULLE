<script>
    let current = 'top';
</script>

<div id="TopBar">
    <div class="{current === 'top' ? 'activate' : ''}"
	on:click="{() => current = 'top'}">TOP</div>
    <div class="{current === 'recent' ? 'activate' : ''}"
	on:click="{() => current = 'recent'}">RECENT</div>   
    <div class="{current === 'media' ? 'activate' : ''}"
	on:click="{() => current = 'media'}">MEDIA</div></div>

<style lang="scss">
    @import '../styles/color.scss';

    #TopBar {
        display: flex;
        color: $font-variation;
        border-radius: 10px;
        padding:10px;
        border: solid $tertiary 2px;
        justify-content: space-around;

        &>div{
            cursor: pointer;

            &:hover{
                color: $font;
            }
        }

        .activate{
            color: $font;
            font-weight: bold;
        }
    }
    
</style>
