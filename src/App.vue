<template>
    <div id="app">
        <b-navbar>
            <b-navbar-nav v-b-scrollspy:content>
                <b-navbar-brand class="px-2 pl-3 exo-2 font-weight-normal text-white" style="font-size: 1.5em;">
                    Sojourner & Spirit
                </b-navbar-brand>
                <b-nav-item href="#sojourner" link-classes="open-sans text-white"
                            @click="scrollIntoView">
                    Sojourner
                </b-nav-item>
                <b-nav-item href="#spirit" link-classes="open-sans text-white" @click="scrollIntoView">
                    Spirit
                </b-nav-item>
            </b-navbar-nav>
        </b-navbar>
        <div id="content" ref="content">
            <b-jumbotron fluid container-fluid class="text-dark my-0 py-md-5 py-sm-0 px-md-5 px-sm-3">
                <b-row class="px-sm-3 px-md-3 w-100" align-h="around">
                    <b-col md="6" xl="5" align-self="center">
                        <h1 id="sojourner">
                            Sojourner
                        </h1>
                        <p class="ml-4">
                            Launched into space on
                            <em class="text-nowrap" :title="this.moments.sojourner.launch.fromNow()">
                                {{ this.moments.sojourner.launch.format("MMMM Do, YYYY") }}
                            </em>,
                            Sojourner is the first wheeled vehicle to rove upon another planet - Mars.
                            It landed on <em class="text-nowrap" :title="this.moments.sojourner.landing">July 4th,
                            1997</em> in the <em>Ares Vallis</em> region.
                        </p>
                        <p class="ml-4">
                            Despite it's original mission duration planned to be just 7 days, it stayed active for 83
                            days in total.
                        </p>
                        <p class="ml-4">
                            The lander that Sojourner landed on, <em>Pathfinder</em>, used Airbags, paving the way for
                            the technologies use in future missions, such as Curiosity and Spirit.
                        </p>
                    </b-col>
                    <b-col md="6" xl="3" align-h="center" class="w-100 h-100">
                        <b-carousel
                                :interval="4000"
                                img-width="400"
                                img-height="400"
                                style="text-shadow: 6px 5px 8px black;"
                        >
                            <b-carousel-slide
                                    caption="Mars Pathfinder Logo"
                                    img-src="./assets/pathfinder_logo.jpg"></b-carousel-slide>
                            <b-carousel-slide
                                    caption="Sojourner Rover"
                                    img-src="./assets/sojourner.jpg"></b-carousel-slide>
                        </b-carousel>
                        <b-img fluid-grow src=""></b-img>
                    </b-col>
                </b-row>
            </b-jumbotron>
            <b-jumbotron fluid container-fluid class="bg-black my-0 py-md-5 py-sm-0 px-md-5 px-sm-3">
                <b-row class="px-sm-3 px-md-3 w-100" align-h="around">
                    <b-col md="6" xl="3" align-h="center">
                        <b-carousel
                                :interval="4000"
                                img-height="400"
                                img-width="400"
                                style="text-shadow: 6px 5px 8px black;"
                        >
                            <b-carousel-slide
                                    caption="Spirit Rover"
                                    img-src="./assets/spirit.jpg"></b-carousel-slide>
                        </b-carousel>
                        <b-img fluid-grow src=""></b-img>
                    </b-col>
                    <b-col class="ml-n5" md="6" xl="5" align-self="center">
                        <h1 id="spirit">
                            Spirit
                        </h1>
                        <p class="ml-4">
                            The geology-centric rover was launched into space <abbr
                                title="Spirit and Opportunity were launched separately, 3 days apart.">with it's
                            twin</abbr>, Opportunity, on
                            <em class="text-nowrap" :title="this.moments.spirit.launch.fromNow()">
                                {{ this.moments.spirit.launch.format("MMMM Do, YYYY") }}</em>, and on
                            <em :title="this.moments.sojourner.landing.fromNow()">
                                {{ this.moments.spirit.landing.format("MMMM Do, YYYY") }}
                            </em>, it became the 2nd rover to arrive on the red planet.
                        </p>
                        <p class="ml-4">
                            Spirit was planned with just a 90 day mission in mind, but like it's twin, Spirit outlasted
                            this cycle far beyond what was originally planned.
                        </p>
                        <p class="ml-4">
                        </p>
                    </b-col>
                </b-row>
            </b-jumbotron>
        </div>
    </div>

</template>

<style lang="scss">
    @import url('https://fonts.googleapis.com/css2?family=Exo+2:wght@500&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,400;0,600;0,700;1,400&display=swap');
    @import "./scss/_variables.scss";


    .jumbotron {
        color: $white;

        p {
            @extend .open-sans;
            font-size: 1.3em;
        }
    }

    abbr {
        text-decoration-color: rgba(255, 255, 255, 0.5) !important;
    }

    .bg-black {
        background-color: $primary;
        color: $white;
    }

    .nav {
        @extend .bg-black;
    }

    .jumbotron h1 {
        @extend .exo-2;
        font-size: 2.1em;
    }

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

    .navbar-brand, .nav-link {
        font-size: 1.2em;
        color: $white;
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
    import moment from 'moment';

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
            },
        },
        data() {
            return {
                moment: moment,
                dates: {
                    sojourner: {
                        launch: [1996, 11, 4, 5, 57],
                        landing: [1997, 6, 4],
                        lastContact: [],
                    },
                    spirit: {
                        launch: [2003, 5, 11, 16, 57],
                        landing: [2004, 0, 4, 3, 34],
                        lastContact: []
                    }
                },
            }
        },
        computed: {
            moments: function () {
                moment.defaultFormat = "MMMM Do, YYYY";
                let obj = {}
                // Build moment.utc fromNow 2d object dict
                for (let k in this.dates) {
                    if (!(k in obj))
                        obj[k] = {}

                    for (let j in this.dates[k]) {
                        obj[k][j] = moment.utc(this.dates[k][j])
                    }
                }
                return obj;
            }
        }
    }
</script>
