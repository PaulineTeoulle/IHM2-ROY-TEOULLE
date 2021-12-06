<script>	
    import Actu from "../components/Actu.svelte";
    import RightBar from "../components/RightBar.svelte";
    import Modal from "../components/Modal.svelte";

    let posts = [
		{"user" : "Sxyrp", "thumbnail": "kiwi.jpg", "game" : "Dofus", "message" : "Quête tutu presque terminée !!! Demain gros rush temporis (bougle dj gelé pour drop le gelano) :p", "image" : "tutu.png", "comments" : "13", "likes" : 70, "date" : "13 nov. 2021"},
		{"user" : "Bamboo", "thumbnail": "scratch.jpg", "game" : "Dofus", "message" : "Caverne des Bworks", "image" : "caverne.png" ,"comments" : "8", "likes" : 53, "date" : "12 nov. 2021"}
	]

    function addPost(event){
		posts = [...posts, {"user" : "Pryxs", "thumbnail": "casimirFace.png", "game" : "Dofus", "message" : `${event.detail.text}`, "image" : "ougah.PNG", "comments" : "0", "likes" : "0", "date" : "9 dec. 2021"}]
	}
</script>

<script context="module">
    export function toggleModal(){
        let modal = document.getElementsByClassName("Modal")[0]
        let bg = document.getElementsByClassName("background")[0]
        let style = getComputedStyle(modal).display;

        switch(style){
            case "none":
                modal.style.display = "block";
                bg.style.display = "block";
                break;
            case "block":
                modal.style.display = "none";
                bg.style.display = "none";
                break;
            default:
                break;
        }
    }

  
</script>

<main>
    <Actu posts={posts}/>
    <RightBar /> 
    <Modal on:message={addPost}/>
</main>

<style lang="scss">
    @import '../styles/home.scss';
</style>