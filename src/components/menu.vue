<template>
    <header :class >

        <div v-if="extraHeader">
            <div class="site-logo" :class="logoColor" >Wild Rydes  </div>
             
            <div class="row column medium-8 large-6 xlarge-5 xxlarge-4">
            <h1 class="">{{title}}</h1>
            <p class="content">
                {{content}} 
            </p>
            </div>
        </div>

        <h1  v-show="showTitle" class="title">Wild Rydes</h1>
        <nav  id="nav"  v-show="isOpen" class="site-nav">
            <ul>
                <li><router-link to="/">Home</router-link></li> 
                <li><router-link to="/unicorns">Meet the Unicorns</router-link></li> 
                <li><router-link to="/investors">Investors &amp; Board of Directors</router-link></li> 
                <li><router-link to="/faq">FAQ</router-link></li> 
                <li> <router-link to="/apply">Apply</router-link> </li>
                <li> <a href="/auth">Register</a> </li>
            </ul>
        </nav>
        <div :class="menuStatus">
            <button @click='toggle()' type="button" class="btn-menu"><span>Menu</span></button>
        </div>
        <a  v-show="showTitle" class="home-button" href="/auth">Giddy Up Bro! </a>
    </header>
</template>

<script>
export default {
  name: 'menu',
  props: ['showTitle','extraHeader','title', 'content','logoColor'],
  data () {
      return {
            isOpen: false, 
            menuStatus:'',
      }
    },
  methods: {
    toggle: function () {  
       this.isOpen = !this.isOpen
       if(!this.menuStatus){
        this.menuStatus="menu-opened"
       }else{
         this.menuStatus=""
        }
    }
  }
}

</script>
