<div id="Search">
    <input
        id="searchInput"
        type="text"
        name="fname"
        placeholder="Rechercher sur Herobrine"
    /><br />
</div>

<style>
    #Search {
        color: aqua;
        margin-right: 20px;
    }

    #searchInput {
        width: 100%;
        border-radius: 10px;
        background-color: #444444ff;
        border: 0;
        padding: 10px;
        color: white;
        background-image: url("/images/svg/loupe.svg");
        background-size: contain;
        background-repeat: no-repeat;
        text-indent: 70px;
        transition: 0.2s;
    }

    ::placeholder {
        color: #b9b9b9ff;
        font-size: large;
    }

    #searchInput:focus {
        background-image: none;
        text-indent: 0px;
    }
</style>
