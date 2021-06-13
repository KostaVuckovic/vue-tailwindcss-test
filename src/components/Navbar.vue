<template>
  <header class="header fixed z-50 top-0 left-0 right-0 bg-white transition-all duration-300 ease-out font-body" :class="{ 'navbar-hidden' : !showNavbar }">
    <nav class="navigation relative flex items-center justify-between h-16 px-6 lg:max-w-5xl mx-auto">
      <!-- logo -->
      <router-link to="/">
        <svg viewBox="0 0 118 18" xmlns="http://www.w3.org/2000/svg" class="w-20"><g fill-rule="evenodd"><path d="M11.425 0v7.07H3.55V0H0v18h3.55v-7.556h7.875V18H15V0zM26 0v18h12v-3.32h-8.39v-4.182h8.212V7.205H29.61V3.293H38V0zM49 0v18h10v-3.373h-6.651V0zM90 18h3V0h-3z"></path> <path d="M75.184 14.735c1.36 0 2.165-.837 2.165-2.132 0-1.134-.755-2.105-2.165-2.105h-4.608v4.237h4.608zm-.126-7.503c1.208 0 1.964-.836 1.964-1.997 0-1.106-.756-1.97-1.964-1.97h-4.482v3.967h4.482zM67 0h8.838c3.198 0 4.835 2.186 4.835 4.588 0 2.267-1.31 3.778-2.896 4.129C79.565 9.013 81 10.876 81 13.142 81 15.841 79.313 18 76.115 18H67V0z" fill-rule="nonzero"></path> <path d="M104 14.896l8.681-11.523H104V0h13.807v3.077l-8.681 11.55H118V18h-14z"></path></g></svg>
      </router-link>
      <!-- hamburger menu button -->
      <button @click="hamburgerMenuOpened = !hamburgerMenuOpened" class="focus:outline-none z-40 lg:hidden">
        <svg viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg" class="hamburger fill-current stroke-current transition-colors duration-500 w-6" :class="{ openNav: hamburgerMenuOpened }">
          <line x1="1" x2="19" y1="4" y2="4" class="line1 transition-all duration-500"></line> 
          <line x1="1" x2="19" y1="9" y2="9" transform="rotate(0 10 9)" class="line2 origin-center transition-all duration-500"></line> 
          <line x1="1" x2="19" y1="9" y2="9" transform="rotate(0 10 9)" class="line3 origin-center transition-all duration-500"></line> 
          <line x1="1" x2="19" y1="14" y2="14" class="line4  transition-all duration-500"></line>
        </svg>
      </button>
      <!-- hamburger menu content -->
      <div class="screen-menu h-screen fixed overflow-y-auto inset-0 bg-white z-30 transition-transform duration-500 lg:hidden" :class="{ 'menuDown': hamburgerMenuOpened }">
        <div class="relative pt-16 bg-white w-full h-10">
          <router-link to="/" class="absolute top-6 left-6">
            <svg viewBox="0 0 118 18" xmlns="http://www.w3.org/2000/svg" class="w-20" data-v-182e8fe4=""><g fill-rule="evenodd"><path d="M11.425 0v7.07H3.55V0H0v18h3.55v-7.556h7.875V18H15V0zM26 0v18h12v-3.32h-8.39v-4.182h8.212V7.205H29.61V3.293H38V0zM49 0v18h10v-3.373h-6.651V0zM90 18h3V0h-3z"></path> <path d="M75.184 14.735c1.36 0 2.165-.837 2.165-2.132 0-1.134-.755-2.105-2.165-2.105h-4.608v4.237h4.608zm-.126-7.503c1.208 0 1.964-.836 1.964-1.997 0-1.106-.756-1.97-1.964-1.97h-4.482v3.967h4.482zM67 0h8.838c3.198 0 4.835 2.186 4.835 4.588 0 2.267-1.31 3.778-2.896 4.129C79.565 9.013 81 10.876 81 13.142 81 15.841 79.313 18 76.115 18H67V0z" fill-rule="nonzero"></path> <path d="M104 14.896l8.681-11.523H104V0h13.807v3.077l-8.681 11.55H118V18h-14z"></path></g></svg>
          </router-link>
          <button class="absolute right-16 top-3 py-2 px-5 bg-black text-white font-bold text-sm">Login</button>
          <div class="relative">
            <ul class="no-underline flex p-5 font-bold bg-gray-100">
              <li><a href="#" @click="borderL">Our Product</a></li>
              <li class="ml-3"><a href="#" @click="borderR">Our Company</a></li>
            </ul>
            <div class="borderBottom absolute bottom-0 left-5 border-t border-2 border-blue-500 w-24 transition-all duration-700" :class="{'borderRight' : !borderLeft}"></div>
          </div>
          <!-- left and right links -->
          <div class="p-5 divide-y-2 divide-gray-200 font-bold transition-all duration-500">
            <transition name="fade" mode="out-in">
              <ul v-if="borderLeft">
                <li class="mb-6"><router-link to="#">Mobility</router-link></li>
                <li class="mb-6"><router-link to="#">Helbiz Kitchen</router-link></li>
                <li class="mb-6"><router-link to="#">Helbiz Live</router-link></li>
                <li class="mb-6"><router-link to="#">Investors</router-link></li>
                <li class="mb-4"><router-link to="#">Unlimited</router-link></li>
              </ul>
              <ul class="border-b-2 border-gray-200" v-else>
                <li class="mb-6 font-bold "><router-link to="#">About</router-link></li>
                <li class="mb-6 font-bold "><router-link to="#">Company Info</router-link></li>
                <li class="mb-6 font-bold "><router-link to="#">Sustainability</router-link></li>
                <li class="mb-6 font-bold "><router-link to="#">Safety</router-link></li>
                <li class="font-bold mb-6"><router-link to="#">Partners</router-link></li>
                <li class="font-bold mb-6"><router-link to="#">Newsroom</router-link></li>
                <li class="font-bold mb-6"><router-link to="#">Cities</router-link></li>
                <li class="font-bold mb-6"><router-link to="#">Advertising</router-link></li>
                <li class="font-bold mb-4"><router-link to="#">Support</router-link></li>
              </ul>
            </transition>
            <ul class="py-4">
              <li class="mb-6"><router-link to="#">Privacy policy</router-link></li>
              <li class=""><router-link to="#">Contact Us</router-link></li>
            </ul>
            <div class="flex pt-4">
              <a href="#" class="flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 36 36" class="w-8 h-8 mr-4"><defs><circle id="icon_en_a" cx="18" cy="18" r="18"></circle></defs> <g fill="none" fill-rule="evenodd"><mask id="icon_en_b" fill="#fff"><use xlink:href="#icon_en_a"></use></mask> <use fill="#D8D8D8" xlink:href="#icon_en_a"></use> <g mask="url(#icon_en_b)"><path fill="#FFF" d="M0 0h54.486v36H0z"></path> <path fill="#D80027" d="M0 3.998h54.486v4.566H0zm0 9.134h54.486v4.566H0zm0 9.132h54.486v4.566H0zm0 9.133h54.486v4.566H0z"></path> <path fill="#2E52B2" d="M0 0h27.243v19.459H0z"></path> <path fill="#F0F0F0" d="M11.017 8.572l-.452 1.274H9.102l1.184.786-.453 1.273 1.184-.786 1.183.786-.452-1.273 1.184-.786h-1.463zm.452 5.868l-.452-1.273-.452 1.273H9.102l1.184.787-.453 1.273 1.184-.786 1.183.786-.452-1.273 1.184-.787zm-6.183 0l-.452-1.273-.452 1.273H2.919l1.184.787L3.65 16.5l1.184-.786 1.183.786-.452-1.273 1.184-.787zm-.452-5.868l-.452 1.274H2.919l1.184.786-.453 1.273 1.184-.786 1.183.786-.452-1.273 1.184-.786H5.286zm6.183-4.595l-.452 1.274H9.102l1.184.786-.453 1.273 1.184-.786 1.183.786-.452-1.273 1.184-.786h-1.463zm-6.183 0l-.452 1.274H2.919l1.184.786L3.65 7.31l1.184-.786 1.183.786-.452-1.273 1.184-.786H5.286zM17.2 8.572l-.452 1.274h-1.463l1.183.786-.452 1.273 1.184-.786 1.183.786-.452-1.273 1.183-.786h-1.463zm.451 5.868l-.451-1.273-.452 1.273h-1.463l1.183.787-.452 1.273 1.184-.786 1.183.786-.452-1.273 1.183-.787zm6.183 0l-.451-1.273-.453 1.273h-1.462l1.183.787-.452 1.273 1.184-.786 1.183.786-.453-1.273 1.184-.787zm-.451-5.868l-.453 1.274h-1.462l1.183.786-.452 1.273 1.184-.786 1.183.786-.453-1.273 1.184-.786h-1.463zM17.2 3.977l-.452 1.274h-1.463l1.183.786-.452 1.273 1.184-.786 1.183.786-.452-1.273 1.183-.786h-1.463zm6.183 0l-.453 1.274h-1.462l1.183.786-.452 1.273 1.184-.786 1.183.786-.453-1.273 1.184-.786h-1.463z"></path></g></g></svg>
                <p class="font-bold">English(US)</p>
              </a>
            </div>
          </div>
        </div>
      </div>
      <!-- laptop and desktop links navigation -->
      <div class="hidden lg:flex lg:items-center font-semibold" style="font-size: 10px;">
        <ul class="flex uppercase tracking-widest">
          <li class="m-4"><router-link to="#">Mobility</router-link></li>
          <li class="m-4"><router-link to="#">Helbiz kitchen</router-link></li>
          <li class="m-4"><router-link to="#">Helbiz live</router-link></li>
          <li class="m-4"><router-link to="#">Investors</router-link></li>
          <li class="m-4"><router-link to="#">Unlimited</router-link></li>
          <li class="m-4"><router-link to="#" @click="openAbout">About</router-link></li>
        </ul>
        <a href="#" class="px-2 mr-4 lg:border-l lg:border-r lg:border-gray-300 uppercase font-medium tracking-widest flex items-center">
          <p>Eng</p>
          <svg xmlns="http://www.w3.org/2000/svg" width="8" height="5" viewBox="0 0 8 5" class="ml-1"><path fill="none" fill-rule="evenodd" d="M1363 33L1366.103 36.103 1369.206 33" transform="translate(-1362 -32)" class="stroke-current"></path></svg>
        </a>
        <router-link to="#" class="px-6 py-2 bg-black text-white font-bold text-sm">Login</router-link>
      </div>
      <!-- about menu -->
      <div class="about-menu hidden lg:block lg:fixed left-0 right-0 bottom-0 z-40  bg-white transition-transform duration-500 h-screen" :class="{ 'open-about' :aboutOpened }">
        <div class="container flex justify-between items-start h-full p-5 mx-auto lg:max-w-5xl">
          <ul class="font-bold text-2xl">
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">About</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Company Info</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Sustainability</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Safety</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Partners</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Newsroom</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Cities</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Advertising</router-link></li>
            <li class="mb-4 hover:text-blue-400 transition-colors duration-150"><router-link to="#">Support</router-link></li>
          </ul>
          <button @click="openAbout" class="hover:text-blue-400 focus:outline-none">
            <svg viewBox="0 0 22 22" xmlns="http://www.w3.org/2000/svg" class="fill-current stroke-current duration-500 w-8 h-8"><line x1="1" x2="20" y1="20" y2="1" style="stroke-width: 4;"></line> <line x1="1" x2="20" y1="1" y2="20" style="stroke-width: 4;"></line></svg>
          </button>
        </div>
      </div>
      
    </nav>
  </header>
</template>

<script>
import { ref } from '@vue/reactivity'
import { onBeforeUnmount, onMounted } from '@vue/runtime-core'
export default {
  name: 'Navbar',
  setup(){
    // hamburger menu
    const hamburgerMenuOpened = ref(false)
    
    // border animation in hamburger menu
    const borderLeft = ref(true)

    const borderR = () => {
      document.querySelector('.borderBottom').style.left = "130px"
      document.querySelector('.borderBottom').style.width = "110px"
      borderLeft.value = false
    }

    const borderL = () => {
      document.querySelector('.borderBottom').style.left = "20px"
      document.querySelector('.borderBottom').style.width = "96px" 
      borderLeft.value = true     
    }

    // navbar scroll animation
    const showNavbar = ref(true)
    const lastScrollPosition = ref(0)

    const onScroll = () => {
        // Get the current scroll position
        const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
        // Because of momentum scrolling on mobiles, we shouldn't continue if it is less than zero
        if (currentScrollPosition < 0) {
          return
        }
        // Here we determine whether we need to show or hide the navbar
        showNavbar.value = currentScrollPosition < lastScrollPosition.value
        // Set the current scroll position as the last scroll position
        lastScrollPosition.value = currentScrollPosition
      }
    
      onMounted(() => {
        window.addEventListener('scroll', onScroll)
      })

      onBeforeUnmount(() => {
        window.removeEventListener('scroll', onScroll)
      })

      // about section navbar
      const aboutOpened = ref(false)

      const openAbout = () => {
        aboutOpened.value = !aboutOpened.value
        document.body.style.overflow = aboutOpened.value ? 'hidden' : 'visible';
      }

    return{
      hamburgerMenuOpened,
      borderLeft,
      borderL,
      borderR,
      showNavbar,
      aboutOpened,
      openAbout
    }
  }
}
</script>

<style>
/* hamburger menu animation */
.hamburger.openNav .line1{
  opacity: 0;
}
.hamburger.openNav .line2{
  transform: rotate(45deg)
}
.hamburger.openNav .line3{
  transform: rotate(-45deg)
}
.hamburger.openNav .line4{
  opacity: 0;
}
.screen-menu{
  transform: translate3d(0, -100%, 0);
}
.menuDown{
  transform: translate3d(0, 0, 0);
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity .5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
/* hide navbar when scroll down */
.header{
  transform:translate3d(0,0,0)
}
.navbar-hidden{
  transform: translate3d(0, -100%, 0);
}
/* about menu */
.about-menu{
  transform: translate3d(0, -100%, 0);
  top: 0;
}
.open-about{
  transform:translate3d(0,0,0);
  top: 96px;
}
@media screen and (min-width: 1392px) {
  nav{
    max-width: 1392px;
  }
}
</style>