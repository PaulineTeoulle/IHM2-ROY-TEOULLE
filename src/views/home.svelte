<script>	
import Actu from "../components/Actu.svelte";
// import LeftBar from "./LeftBar.svelte";
import RightBar from "../components/RightBar.svelte";
import Modal from "../components/Modal.svelte";
</script>

<script context="module">
    export function toggleModal(){
        let modal = document.getElementsByClassName("Modal")[0]
        let bg = document.getElementsByClassName("background")[0]
        let style = getComputedStyle(modal).display;
        console.log(modal)
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
    <Actu />
    <RightBar /> 
    <Modal/>
</main>

<style lang="scss">
    @import '../styles/home.scss';
</style>