<!-- You may notice this navbar is not responsive-->
<!-- We would like you to style it so it is responsive-->
<!-- You do not need to make the dropdown menu on the "Featured Collections" -->

<!-- This is the Navbar which contains the desktop and mobile navbar and the one shown depends
on the size of the screen and whether the hamburger button shown on smaller screens is clicked.
It uses transitions to make the switch between the desktop and mobile navbar smoother.  -->

<template>
<div class="container">
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css" rel="stylesheet">
      <Transition name="fade">
        <div class="desktop-navbar" v-if="!hamburgerButtonClicked">
        <div class="navbar_container">
            <img class="nav_banner" src="https://res.cloudinary.com/risidio/image/upload/v1633609222/RisidioMarketplace/gradienta-m_-1_v4hs5p.svg" alt="">
        </div>
        <div class = "mainNavbar">
            <ul class="main-navbar-items">
            <div class="site-logo">
              <img :src="logo" alt="risidio-logo"/>
              <p>Marketplace</p>
            </div>
            <div @click="toggleMobileMenu" class="hamburger-menu">
                <i class="fas fa-bars"></i>
            </div>
            <li class="nav-item" > Explore </li>
                <li class="nav-item collections-nav-item"> 
                    Featured Collections &nbsp; 	<i class="fas fa-caret-down"></i>
                    <span class="collections-dropdown-menu">
                        <ul>
                          <li><a href="#">Collection 1</a></li>
                          <li><a href="#">Collection 2</a></li>
                          <li><a href="#">Collection 3</a></li>
                        </ul>
                    </span>
                </li>
                <li class="nav-item right"> How It Works</li>
                <li class="nav-item"> About Risidio</li>
                <li class="nav-item navbar-button violet-button"> My NFTs</li>
            </ul>
         </div>
    </div>
      </Transition>
    <div class="mobile-navbar-wrapper">
      <Transition name="slide-fade">
        <MobileNavbar @toggle-mobile-menu="toggleMobileMenu" v-if="hamburgerButtonClicked" />
      </Transition>
    </div>
    </div>
</template>

<script>

// This is the data, methods, and imported components. This includes the
// Risidio logo, boolean value for hamburgerButtonClicked which determines
// whether to show the full mobile navbar menu or not. It also imports the
// MobileNavbar component to be displayed if the hamburger button is clicked.

import MobileNavbar from "./MobileNavbar.vue";

export default {
  data () {
    return{
      hamburgerButtonClicked: false,
      logo: 'https://res.cloudinary.com/risidio/image/upload/v1633609248/RisidioMarketplace/Group_-1_fgpanq.svg',
    }
  },
  methods: {
      toggleMobileMenu() {
          this.hamburgerButtonClicked = !this.hamburgerButtonClicked;
      }
  },
  components: {
    MobileNavbar
  }
}
</script>

<style scoped>
.navbar-button {
  background-color: rgba(256,256,256, 0.1);
  color: #5FBDC1 !important;
}

.container {
    grid-template-rows: 1fr 1fr 1fr; /* or whatever you need */
}

.mainNavbar{
  margin: 0 50px 0 50px;
}
.mainNavbar ul {
  display: flex;
  flex-direction: row;
  text-decoration: none;
  align-items: center;
  margin: 0;
  padding-bottom: 20px;
}
.risidio-logo{
    align-self: flex-start;
}
.nav-item{
  list-style-type: none;
  margin: 0 20px;
  color: white;
  font-size: 12px;
  line-height: 15px;
  cursor: pointer;
}
.right {
    margin-left: auto;
}
.nav_banner{
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 120px;
  object-fit: cover;
  z-index: -11;
}

/*

CSS file compiled from scss file to implement other styles.

*/

@import '../../assets/style.css';

/*

Styles for transitions

*/

.fade-enter-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.slide-fade-enter-active {
  transition: all 0.4s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}

</style>