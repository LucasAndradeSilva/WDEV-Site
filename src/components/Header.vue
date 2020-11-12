<template>
    <header>
        <nav class="container">
            <a href="/">
                <img alt="WDEV" id="logo" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg"/>
            </a>

            <img alt="Abrir Menu" v-on:click="openMenu" id="menu-button" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/menu.svg"/>

            <div id="menu-overlay" v-on:click="closeMenu" v-if="menuActive"></div>

             <div id="menu-items" :class="{active: menuActive}" >

                    <img alt="Abrir Menu" id="menu-logo" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg"/>

                    <ul>
                        <li>
                            <a href="/"> Home </a>
                        </li>

                        <li>
                            <a href="/videos"> Vídeos </a>
                        </li>

                        <li>
                            <a href="/sobre"> Sobre </a>
                        </li>

                        <li>
                            <a href="/contato"> Contato </a>
                        </li>
                    </ul>
                </div>

        </nav>
    </header>
</template>

<script>
export default {
    name: 'Header', //Realizar uma importação dessa vue vai charmar Header
    data(){
        return{
            menuActive: false
        }
    },
    methods: {

        openMenu: function(){
            this.menuActive = true;
        },

        closeMenu: function(){
            this.menuActive = false;
        }
    },
}
</script>

<style scoped> 
    header{
        background-color: var(--color-background-nav);
        width: 100%;
        height: 60px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    nav{
        display: flex;
        justify-content: space-between;
        height: 60px;
        align-items: center;
    }

    #logo{
        width: 130px;
    }

    #menu-button{
        width: 30px;
        cursor: pointer;
    }

    #menu-overlay{
        position: fixed;
        top: 0;
        left: 0;        
        width: 40%;
        height: 100vh;
        background-color: #000000;
        opacity: 0.8;
    }

    #menu-logo{
        width: 110px;
        margin-top: 30px;
        margin-bottom: 10px;        
    }

    #menu-items{
        position: fixed;
        top: 0;
        right: 0;
        background-color: var(--color-background-nav);
        width: 60%;
        height: 100vh;
        display: none;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        opacity: 0.8;
    }

    #menu-items.active{
        display: flex;
    }

    ul{
        list-style: none;
        text-align: center;
    }

    ul li{
        margin: 20px 0px;
    }

    ul li a{
        color: var(--color-text-light);
    }

    @media (min-width: 700px) {
        #menu-button,
        #menu-logo,
        #menu-overlay{
            display: none;
        }

        #menu-items{            
            display: flex;
            position: static;
            height: 60px;
            width: auto;            
        }

        ul{
            display: flex;
            height: 60px;
            align-items: center;
        }

        ul li{
            margin: 0;
            margin-left: 20px;
        }
    }

</style>