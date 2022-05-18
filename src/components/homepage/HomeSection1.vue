<!-- This is the first main section of the homepage. It contains the name,
descriptions, artist, and key numbers of the collection. It also has a tabbed panel
which determines whether to show the items in the collection or the activity of which
there is none at the moment.  -->

<template>
  <div class="section-1-container">
    <div class="collection-banner">
    <h2>Pokemon Collection</h2>
  </div>
  <div class="collection-banner-placeholder"></div>
  <div class="collection-description">
    <div class="artist-avatar"></div>
    <h3 class="artist-name">Jane Smith</h3>
    <p class="nft-and-collectable-description">
      Description of the NFT/collectable - Each NFT in this collection is
      a picture or gif related to pokemon. This is to demonstrate to artist's
      love of pokemon as a video game series, and how it really is a work of art
      to them.
    </p>
    <p v-if="moreTextDisplayed" class="collection-description-description-paragraph">
      Description of this collection - The content of the NFTs is all related
      to pokemon. The owner of this collection is a massive pokemon fan
      and wants it to be recognised in this exciting new world of blockchain,
      decentralisation and NFTs. They envision a future of pokemon in the metaverse
      where you can immerse yourself in the exciting world of pokemon, and really
      feel like a Pokemon trainer.
    </p>
    <br />
    <button @click="toggleMoreText" class="read-more-button"><b v-if="!moreTextDisplayed">Read More</b><b v-if="moreTextDisplayed">Hide</b></button>
    <br />
    <br />
    <div class="collection-key-numbers">
      <div class="floor-price">
        <h5>Floor Price</h5>
        <b>2,835 STX</b>
      </div>
      <div class="owners">
        <h5>Owners</h5>
        <b>1,236</b>
      </div>
      <div class="items">
        <h5>Items</h5>
        <b>2,500</b>
      </div>
    </div>
    <br />
    <br />
    <div class="items-and-activity-tab-panel">
      <div @click="selectTabbedPanelOption1" :style="panel1Selected ? selectedPanelStyle : null" class="option"><b>Items</b></div>
      <div @click="selectTabbedPanelOption2" :style="panel2Selected ? selectedPanelStyle : null" class="option"><b>Activity</b></div>
    </div>
  </div>
  </div>
</template>

<script>

// Here I've used v-if attributes, data, and methods to implement the
// read more feature as well as the tabbed panel which determines whether
// the collection activities of NFTs are displayed. This is achieved through
// the emit keyword which emits a word onto the parent component which that parent
// component than acts on by activating a certain one of it's methods.

export default {
  data(){
    return {
      moreTextDisplayed: false,
      panel1Selected: true,
      panel2Selected: false,
      selectedPanelStyle: {
        color: "#50B1B5",
        borderBottom: "1px solid #50B1B5"
      }
    }
  },
  name: 'HomeSection1',
  methods: {
    toggleMoreText(){
      this.moreTextDisplayed = !this.moreTextDisplayed;
    },
    selectTabbedPanelOption1(){
      this.panel1Selected = true;
      this.panel2Selected = false;
      this.$emit('items-panel-selected');
    },
    selectTabbedPanelOption2(){
      this.panel2Selected = true;
      this.panel1Selected = false;
      this.$emit('activity-panel-selected');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  overflow-x: hidden;
}

.collection-banner h2 {
  font-weight: normal;
  margin: 0;
  color: white;
}

.collection-banner {
  background-image: url("../../assets/pokemon-nfts-banner-3.jpg");
  height: 20vh;
  display: flex;
  left: 0px;
  position: absolute;
  align-items: center;
  justify-content: center;
  margin: 0;
  background-size: contain;
  width: 100%;
  margin-top: 7px;
  z-index: -1;
}

.collection-banner-placeholder {
  height: 17vh;
}

.collection-description {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.artist-avatar {
  height: 70px;
  width: 70px;
  border: 1px solid white;
  border-radius: 70px;
  background-image: url("../../assets/nft-collection-avatar-1.jpg");
  background-size: contain;
}

.collection-description-description-paragraph {
  width: 60%;
}

.nft-and-collectable-description {
  width: 60%;
}

.read-more-button {
  background: none;
  color: #50B1B5;
  border: none;
  font-size: 1rem;
  cursor: pointer;
}

.collection-key-numbers {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #F9F9F9;
  border-radius: 50px;
  width: 60%;
  height: 100px;
}

.collection-key-numbers div {
  width: 30%;
  border-right: 1px solid rgb(214, 212, 212);
}

.collection-key-numbers div:last-of-type {
  border-right: none;
}

.collection-key-numbers div h5 {
  margin-top: 0;
  margin-bottom: 20px;
  font-weight: normal;
  font-size: 1rem;
}

.items-and-activity-tab-panel {
  border-bottom: 1px solid rgb(214, 212, 212);
  width: 80%;
  display: flex;
  justify-content: center;
  height: 40px;
}

.items-and-activity-tab-panel .option {
  width: 100px;
  cursor: pointer;
}

.items-and-activity-tab-panel .option:last-of-type {
  margin-left: 20px;
}

.option-selected {
  color: rgb(72, 202, 245);
  border-bottom: 1px solid rgb(72, 202, 245);
}

@media(max-width: 750px) {
  .collection-key-numbers {
    margin-top: 10vh;
    flex-direction: column;
    height: 400px;
  }

  .collection-key-numbers div {
    width: 50%;
    margin-top: 5vh;
    padding-bottom: 5vh;
    border-right: none;
    border-bottom: 1px solid rgb(214, 212, 212);
  }

  .collection-key-numbers div:last-of-type {
    border-bottom: none;
  }
}

</style>
