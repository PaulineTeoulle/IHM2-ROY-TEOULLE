<script>
	

</script>


<div class="Banner">
    <img src="images/kiwi.jpg">
    <div>
        <div class="profil"> 
            <img src="images/kiwi.jpg"> 
            <p>Sxyrp</p>
        </div>
        
          <div><pre>129 Abonnements          8 Abonnés</pre></div>   
    </div>
    <button>button</button>
</div>

<style lang="scss">
	@import '../styles/color.scss';

	.Banner{
        background-color: $secondary;
        width: 100%;
        display: flex;
        flex-direction: column;
        

        &>img{
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        &>div{
            position: relative;

            
            &>.profil{
                position: absolute;
                top: -68px;
                left: 25px;

                &>img{
                    width: 128px;
                    height: 128px;
                    border-radius: 50%;
                    object-fit: cover;
                    border: solid 4px $primary;
                }

                & p{
                    margin: 0;
                    text-align: center;
                    font-weight: bold;
                }
            }
        }

        &>div:nth-child(2){
            padding-top:88px;
            display:flex;
            justify-content: end;
            padding-bottom: 16px;
            margin: 0 16px;
            border-bottom: 1px solid $tertiary;
            color: $font;
        }
        &>button{
            width: fit-content;
            padding: 0 10px;
            align-self: flex-end;
            margin: 16px;
        }
    }

</style>
