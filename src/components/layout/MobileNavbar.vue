<template class="mobile-navbar-template">
    
    <Transition name="fade">
        <div class="mobile-navbar-container">
        <div class="navbar_container">
        <img class="nav_banner" src="https://res.cloudinary.com/risidio/image/upload/v1633609222/RisidioMarketplace/gradienta-m_-1_v4hs5p.svg" alt="">
        </div>
    <div class = "mainNavbar">
        <ul class="main-navbar-items">
            <div class="mobile-navbar-header">
                <div class="site-logo">
                <img :src="logo" alt="risidio-logo"/>
                <p>Marketplace</p>
                
            </div>
            <div @click="$emit('toggle-mobile-menu')" class="hamburger-menu-close-button">
                <i class="fas fa-times"></i>
            </div>
            </div>
            <li class="mobile-nav-item" > <b>Explore</b> </li>
            <li class="mobile-nav-item collections-nav-item" > 
                <b>Collections &nbsp;</b> <i class="fas fa-caret-down"></i>
                    <span class="collections-dropdown-menu">
                        <ul>
                          <li><a href="#">Collection 1</a></li>
                          <li><a href="#">Collection 2</a></li>
                          <li><a href="#">Collection 3</a></li>
                        </ul>
                    </span>
            </li>
            <br />
            <hr />
            <br />
            <li class="mobile-nav-item" >How It Works </li>
            <li class="mobile-nav-item" > About Risidio </li>
            <br />
            <br />
            <li class="mobile-nav-item mobile-nav-button violet-button" > Register with Hiro Wallet </li>
        </ul>
    </div>
    </div>
    </Transition>
</template>

<script>
export default {
    data () {
        return{
            logo: 'https://res.cloudinary.com/risidio/image/upload/v1633609248/RisidioMarketplace/Group_-1_fgpanq.svg',
        }
    },
}
</script>

<style scoped>
@import '../../assets/style.css';

.mobile-navbar-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    transition: 0.5s ease all;
}

.collections-dropdown-menu {
    padding: 0 !important;
    width: 75vw;
}

.collections-dropdown-menu li {
    padding-left: 0 !important;
    margin-top: 0 !important;
    height: 30px;
}

.mainNavbar{
  height: 640px;
  position: absolute;
  z-index: 11;
}
.mainNavbar ul {
  display: flex;
  list-style-type: none;
  color: white;
  font-size: 1rem;
  flex-direction: column;
  text-decoration: none;
  align-items: flex-start;
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
  height: 640px;
  object-fit: cover;
  z-index: 2;
}

.main-navbar-items li {
    color: white;
    text-align: left;
    width: 100%;
    margin-top: 5vh;
    padding-left: 5vw;
}

.site-logo{
    justify-self: flex-start;
}

.site-logo p {
    font-size: 1rem;
}

.hamburger-menu-close-button {
    position: absolute;
    right: 1px;
    height: 86.63px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.hamburger-menu-close-button i {
    color: white;
    font-size: 2rem;
    cursor: pointer;
}

.mobile-navbar-header {
    width: 80vw;
    display: flex;
}

hr {
    width: 80vw;
}

.wallet-register-button {
    background-color: rgba(violet, 0.2);
    border-radius: 20px;
    width: 150px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.5s;
}

.mobile-nav-button {
    height: 70px;
    border-radius: 100px;
    padding-left: 0 !important;
}

.mobile-nav-item {
    cursor: pointer;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@media(max-width: 800px){
    @media(min-height: 640px) {
    .nav_banner {
        height: 720px;
    }

    .mainNavbar {
        height: 720px;
    }
}

@media(min-height: 850px) {
    .nav_banner {
        height: 750px;
    }

    .mainNavbar {
        height: 750px;
    }
}
}

</style>