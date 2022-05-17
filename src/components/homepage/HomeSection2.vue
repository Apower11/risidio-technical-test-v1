<template>
    <h1 class="section-2-heading">You've seen the Pokemon Collection</h1>
    <br />
    <br />
    <div class="buttons">
        <a href="#" class="gallery-button"><b>Gallery</b></a>
        <a href="#" class="go-to-top-button"><b>Go Back To Top</b></a>
    </div>
    <br />
    <br />
    <br />

</template>

<script>
export default {

}
</script>

<style scoped>
    .section-2-heading {
        font-weight: normal;
    }
    .gallery-button {
        text-decoration: none;
        background-color: #5FBDC1;
        padding: 20px 60px;
        border-radius: 40px;
        color: white;
    }

    .gallery-button:hover {
        background-color: #40bfc4;
        transition: 0.5s ease-in-out all;
    }

    .go-to-top-button {
        margin-left: 100px;
        text-decoration: none;
        background-color: #dff8f8;
        color: #5FBDC1;
        padding: 20px 60px;
        border-radius: 40px;
    }

    .go-to-top-button:hover {
        background-color: #c8f5f5;
        transition: 0.5s ease-in-out all;
    }
    @media(max-width: 570px){
        .buttons {
            display: flex;
            flex-direction: column;
        }

        .buttons button {
            width: 60%;
        }

        .go-to-top-button {
            margin-top: 30px;
            margin-left: 0;
        }
    }
</style>