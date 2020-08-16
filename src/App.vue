<template>
    <div id="app">
        <b-navbar sticky fixed=true>
            <b-navbar-brand class="px-2 pl-3 exo-2 font-weight-normal text-white" style="font-size: 1.5em;">
                Sojourner & Spirit
            </b-navbar-brand>
            <b-navbar-nav v-b-scrollspy:content>
                <b-nav-item href="#sojourner" link-classes="open-sans text-white" @click="scrollIntoView">
                    Sojourner
                </b-nav-item>
                <b-nav-item href="#spirit" link-classes="open-sans text-white" @click="scrollIntoView">
                    Spirit
                </b-nav-item>
                <b-nav-item class="float-right" link-classes="open-sans text-white font-weight-bold" v-if="showBreakpoint">
                    <span class="d-sm-none" style="text-decoration: line-through;">SM</span>
                    <span class="d-none d-sm-inline d-md-none">SM</span>
                    <span class="d-none d-md-inline d-lg-none">MD</span>
                    <span class="d-none d-lg-inline d-xl-none">LG</span>
                    <span class="d-none d-xl-inline">XL</span>
                </b-nav-item>
            </b-navbar-nav>
        </b-navbar>
        <div id="content" ref="content">
            <b-jumbotron fluid container-fluid="fluid" class="text-dark my-0 py-md-5 py-sm-0 px-md-5 px-sm-3">
                <b-row class="px-sm-3 px-md-3 w-100" align-h="between">
                    <b-col cols="12" lg="8" align-self="center">
                        <h1 id="sojourner">
                            Sojourner
                        </h1>
                        <p class="ml-4">
                            Launched into space on
                            <em class="text-nowrap" :title="this.moments.sojourner.launch.fromNow()">
                                {{ this.moments.sojourner.launch.format("MMMM Do, YYYY") }}</em>,
                            Sojourner is the first wheeled vehicle to rove upon another planet - Mars.
                            It landed on <em class="text-nowrap" :title="this.moments.sojourner.landing">July 4th,
                            1997</em> in the <em>Ares Vallis</em> region.
                        </p>
                        <p class="ml-4">
                            Despite it's original mission duration planned to be just 7 days, it stayed active for 83
                            days in total. This rover paved the way for remote exploration on Mars, becoming the
                            blueprint for 3 more rovers.
                        </p>
                    </b-col>
                    <b-col cols="8" lg="4" xl="3" align-self="center" class="w-100 h-100">
                        <b-img fluid-grow src="./assets/sojourner.jpg"></b-img>
                    </b-col>
                </b-row>
            </b-jumbotron>
            <b-jumbotron fluid container-fluid="fluid px-0" class="bg-black my-0 py-md-5 py-0 px-3 px-md-1 px-xl-2">
                <b-row class="px-sm-3 px-md-3 w-100" align-h="around">
                    <b-col cols="8" lg="7" align-self="top">
                        <h3>Communications</h3>
                        <p class="ml-4">
                            Sojourner is unique among the 4 rovers to successfully deploy on Mars in that it required
                            it's lander to stay in communication with Earth. The rover was not equipped with a high gain
                            antenna, which is required in order to communicate with Earth over large distances.
                        </p>
                        <p class="ml-4">
                            This limitation forced the rover to stay within a certain range of the lander, and
                            throughout it's lifetime on Mars, it never traveled more than a few dozen feet from the
                            lander.
                        </p>
                        <h3>Tools</h3>
                        <p class="ml-4 mb-1">
                            Sojourner was designed to study the surface of Mars by collecting and analyzing rock
                            samples, taking pictures and more using the following tools:
                        </p>
                        <ul>
                            <li class="py-1 pt-2">
                                An <abbr title="Alpha Proton X-ray Spectrometer"><em>APXS</em></abbr> for determining
                                elemental composition of soil, rocks and other materials on the surface of Mars.
                            </li>
                            <li class="py-1">
                                <em>Rover Control Software</em> for coordinating movement, studying terrain features,
                                and viewing the nearby area in 3D space.
                            </li>
                            <li class="py-1">
                                <em>Three cameras</em>, one color, two monochrome. However, the operators primiarily
                                used images from the lander's IMP camera system, as it had higher quality on top of
                                having a height advantage over the rover.
                            </li>
                        </ul>
                    </b-col>
                    <b-col md="6" lg="5" align-h="top" class="w-100 h-100">
                        <h3>Autonomy</h3>
                        <p class="ml-3 ml-lg-4">
                            Sojourner was an important step in Robotics due to the nature of the mission.
                            With such a long distance between Mars and Earth, radio communications took around 14
                            minutes to receive, and then another 14 minutes to send back.
                        </p>
                        <p class="ml-3 ml-lg-4">
                            As such, human telegraphed movements too slow for the mission, and while complete autopilot
                            is impossible for such a complex mission, the rovers, landers, and spacecraft made by NASA
                            had to be programmer with autopilot.
                        </p>
                        <p class="ml-3 ml-lg-4">
                            To solve this problem, Sojourner, along with every rover to land on Mars, is equipped with
                            software dedicated to autonomously moving the rover across the martian surface.
                        </p>
                        <p class="ml-3 ml-lg-4">
                            While Sojourner was comparatively basic in it's software's autonomy, the software was
                            helpful to operators in visualizing and telegraphing instructions across the rocky terrain
                            of Ares Vallis.
                        </p>
                    </b-col>
                </b-row>
            </b-jumbotron>
            <b-jumbotron fluid container-fluid class="text-dark my-0 py-md-5 py-sm-0 px-md-5 px-sm-3">
                <b-row class="w-100" align-h="around">
                    <b-col cols="8" lg="4" align-self="center">
                        <b-img fluid-grow class="shadow-lg" src="./assets/spirit.jpg"></b-img>
                    </b-col>
                    <b-col class="ml-n5 pl-lg-5" cols="12" lg="7" align-self="top">
                        <h1 id="spirit">
                            Spirit
                        </h1>
                        <p class="ml-4">
                            The geology-centric rover was launched into space <abbr
                            title="Spirit and Opportunity were launched separately, 3 days apart.">with it's
                            twin</abbr>, Opportunity, on
                            <em class="text-nowrap" :title="this.moments.spirit.launch.fromNow()">
                                {{ this.moments.spirit.launch.format("MMMM Do, YYYY") }}</em>.
                            And on
                            <em :title="this.moments.sojourner.landing.fromNow()">
                                {{ this.moments.spirit.landing.format("MMMM Do, YYYY") }}</em>,
                            it became the 2nd rover to arrive on the red planet.
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
            <b-jumbotron fluid container-fluid="fluid px-0" class="bg-black my-0 py-md-5 py-0 px-3 px-md-1 px-xl-2">
                <b-row class="px-sm-3 px-md-3 w-100" align-h="around">
                    <b-col cols="8" lg="7" align-self="top">
                        <h3>Communications</h3>
                        <p class="ml-4">
                            Sojourner is unique among the 4 rovers to successfully deploy on Mars in that it required
                            it's lander to stay in communication with Earth. The rover was not equipped with a high gain
                            antenna, which is required in order to communicate with Earth over large distances.
                        </p>
                        <p class="ml-4">
                            This limitation forced the rover to stay within a certain range of the lander, and
                            throughout it's lifetime on Mars, it never traveled more than a few dozen feet from the
                            lander.
                        </p>
                        <h3>Tools</h3>
                        <p class="ml-4 mb-1">
                            Sojourner was designed to study the surface of Mars by collecting and analyzing rock
                            samples, taking pictures and more using the following tools:
                        </p>
                        <ul>
                            <li class="py-1 pt-2">
                                An <abbr title="Alpha Proton X-ray Spectrometer"><em>APXS</em></abbr> for determining
                                elemental composition of soil, rocks and other materials on the surface of Mars.
                            </li>
                            <li class="py-1">
                                <em>Rover Control Software</em> for coordinating movement, studying terrain features,
                                and viewing the nearby area in 3D space.
                            </li>
                            <li class="py-1">
                                <em>Three cameras</em>, one color, two monochrome. However, the operators primiarily
                                used images from the lander's IMP camera system, as it had higher quality on top of
                                having a height advantage over the rover.
                            </li>
                        </ul>
                    </b-col>
                    <b-col md="6" lg="5" align-h="top" class="w-100 h-100">
                        <h3>Autonomy</h3>
                        <p class="ml-3 ml-lg-4">
                            Sojourner was an important step in Robotics due to the nature of the mission.
                            With such a long distance between Mars and Earth, radio communications took around 14
                            minutes to receive, and then another 14 minutes to send back.
                        </p>
                        <p class="ml-3 ml-lg-4">
                            As such, human telegraphed movements too slow for the mission, and while complete autopilot
                            is impossible for such a complex mission, the rovers, landers, and spacecraft made by NASA
                            had to be programmer with autopilot.
                        </p>
                        <p class="ml-3 ml-lg-4">
                            To solve this problem, Sojourner, along with every rover to land on Mars, is equipped with
                            software dedicated to autonomously moving the rover across the martian surface.
                        </p>
                        <p class="ml-3 ml-lg-4">
                            While Sojourner was comparatively basic in it's software's autonomy, the software was
                            helpful to operators in visualizing and telegraphing instructions across the rocky terrain
                            of Ares Vallis.
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

$grid-breakpoints: (
  xs: 0,
  sm: 456px,
  md: 789px,
  lg: 900px,
  xl: 1450px
);

@import '~bootstrap/scss/bootstrap';
@import '~bootstrap/scss/_mixins';
@import '~bootstrap-vue/src/index.scss';

html {
    font-size: 0.8rem;
}

@include media-breakpoint-up(sm) {
    html {
        font-size: 0.9rem;
    }
}

@include media-breakpoint-up(md) {
    html {
        font-size: 1.0rem;
    }
}

@include media-breakpoint-up(lg) {
    html {
        font-size: 1.1rem;
    }
}

.jumbotron {
    color: $white;

    p, li {
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

.navbar {
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
            showBreakpoint: process.env.NODE_ENV === 'development',
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
