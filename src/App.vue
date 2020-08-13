<template>
    <div id="app">
        <b-nav card-header slot="header" v-b-scrollspy:nav-scroller>
            <b-nav-item href="#sojourner-intro" class="font-weight-bolder" @click="scrollIntoView">Sojourner & Spirit
            </b-nav-item>
            <!--            <b-nav-item href="#mdo" @click="scrollIntoView">@mdo</b-nav-item>-->
            <!--            <b-nav-item href="#pi0" @click="scrollIntoView">@pi0</b-nav-item>-->
        </b-nav>
        <b-jumbotron fluid="true" class="text-dark py-5 px-5" container-fluid="true">
            <b-row class="px-3 w-100" align-h="around">
                <b-col md="6" xl="5">
                    <h1 id="sojourner-intro" class="ml-n4">
                        Sojourner
                    </h1>
                    <h3>
                        Sojourner is a robotic Mars rover that landed on July 4, 1997 in the Ares Vallis region.
                        <br>
                        The rover was the first wheeled vehicle to rove another planet, and was part of the Mars
                        Pathfinder mission.
                    </h3>
                </b-col>
                <b-col md="6" xl="3">
                    <b-carousel
                            :interval="5000"
                            indicators
                            img-height="400"
                            img-width="400"
                            style="text-shadow: 4px 2px 2px #333333;"
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
    @import "./scss/_variables.scss";

    .nav-link {
        font-size: 1.2em;
        color: white;
    }

    html, body {
        background-color: $primary;
        color: $white;
        max-width: 100%;
        overflow-x: hidden;
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
