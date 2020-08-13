<template>
    <div id="app">
        <b-nav card-header slot="header" v-b-scrollspy:nav-scroller>
            <b-navbar-brand class="px-2 pl-3 exo-2 font-weight-normal" style="font-size: 1.5em;">
                Sojourner & Spirit
            </b-navbar-brand>
            <b-nav-item href="#sojourner-intro" link-classes="open-sans" @click="scrollIntoView">Sojourner
            </b-nav-item>
            <!--            <b-nav-item href="#mdo" @click="scrollIntoView">@mdo</b-nav-item>-->
            <!--            <b-nav-item href="#pi0" @click="scrollIntoView">@pi0</b-nav-item>-->
        </b-nav>
        <b-jumbotron fluid="true" class="text-dark py-5 px-5" container-fluid="true">
            <b-row class="px-3 w-100" align-h="around">
                <b-col md="6" xl="5" align-self="center">
                    <h2 id="sojourner-intro" class="ml-n4 exo-2">
                        Sojourner
                    </h2>
                    <p class="open-sans" style="font-size: 1.3em;">
                        Launched into space on <em>December 4th, 1996</em>, Sojourner is the first wheeled vehicle to
                        rove upon another planet - Mars.
                        <br>
                        It landed on <em>July 4th, 1997</em> in the <em>Ares Vallis</em>
                        region.
                    </p>
                </b-col>
                <b-col md="6" xl="3">
                    <b-carousel
                            :interval="4000"
                            img-height="400"
                            img-width="400"
                            style="text-shadow: 6px 5px 2px black;"
                    >
                        <b-carousel-slide
                                caption="Mars Pathfinder"
                                img-src="./assets/pathfinder_logo.jpg"></b-carousel-slide>
                        <b-carousel-slide
                                caption="Sojourner"
                                img-src="./assets/sojourner.jpg"></b-carousel-slide>
                    </b-carousel>
                    <b-img fluid-grow src=""></b-img>
                </b-col>
            </b-row>
        </b-jumbotron>
    </div>
</template>

<style lang="scss">
    @import url('https://fonts.googleapis.com/css2?family=Exo+2:wght@500&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,400;0,600;0,700;1,400&display=swap');
    @import "./scss/_variables.scss";

    .carousel-caption {
        bottom: -10px;
    }

    .carousel-caption {
        width: 100%;
        background-size: cover;
        background-color: rgba(0, 0, 0, .45);
        padding-top: 1rem;
        left: 0;
    }

    a {
        text-align: center;

        &:hover {
            color: #b0b0b0;
        }
    }

    .exo-2 {
        font-family: 'Exo 2', sans-serif;
    }

    .open-sans {
        font-family: 'Open Sans', sans-serif;
    }

    .nav-link {
        font-size: 1.2em;
        color: white;
    }

    html, body {
        background-color: $primary;
        color: $white;
        max-width: 100%;
        overflow-x: hidden;
        font-size: 1em;
    }
</style>

<script>
    export default {
        name: 'App',
        components: {},
        methods: {
            scrollIntoView(evt) {
                evt.preventDefault()
                const href = evt.target.getAttribute('href')
                const el = href ? document.querySelector(href) : null
                if (el) {
                    this.$refs.content.scrollTop = el.offsetTop
                }
            }
        }
    }
</script>
