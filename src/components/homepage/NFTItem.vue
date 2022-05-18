<!-- This is the component for a single NFT item which is a box containing the image
and the details of the NFT  -->

<template>
    <div class="nft-item-container">
        <img class="nft-item-image" :src="item.image" alt="" />
        <div class="nft-info-column-1">
            <h3 class="nft-item-name">{{ item.name }}</h3>
            <span class="price-in-stx">{{ item.priceInSTX }} STX</span>
        </div>
        <div class="nft-info-column-2">
            <span class="nft-item-artist">By <b>{{ item.artist }}</b></span>
            <span class="price-in-dollars">{{ item.priceInDollars }} $</span>
        </div>
        <br />
        <br />
    </div>
</template>

<script>
// This component inherits data from the parent component HomeNFTDisplay
// and the data it inherits is that of an NFT item. It inherits it's item
// path, name, artist name, price in STX and price in dollars.

export default {
    props: ['data'],
    data() {
        return {
            item: this.data
        }
    },
}
</script>

<style >
.nft-item-image {
    background-size: cover;
    height: 40vh;
    width: 100%;
    border-radius: 20px;
}

.nft-info-column-1 {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-top: 2vh;
}

.nft-info-column-1 h3 {
    margin: 0;
    text-align: left;
}

.nft-item-name {
    width: 50%;
    text-align: center;
}

.price-in-stx {
    width: 50%;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: flex-end;
}

.nft-item-container {
    background-color: rgba(129, 129, 129, 0.12);
    width: 20vw;
    padding: 20px;
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.nft-item-container:hover {
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    transition: 0.5s ease-in-out all;
}

@media(max-width: 900px){
  .nft-item-container {
    grid-template-columns: 1fr 1fr;
    width: 30vw;
  }
}

@media(max-width: 650px){
  .nft-item-container {
    grid-template-columns: 1fr 1fr;
    width: 70vw;
  }
}

.nft-item-name {
    text-align: left;
    width: 100%;
    font-size: 1.5rem;
    font-weight: normal;
}

.nft-item-artist {
    text-align: left;
    width: 100%;
}

.nft-info-column-2 {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-top: 2vh;
}

.price-in-dollars {
    width: 50%;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: flex-end;
}
</style>