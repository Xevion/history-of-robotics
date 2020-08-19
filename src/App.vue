<template>
    <div id="app">
        <b-navbar class="header py-0" fixed="top">
            <b-navbar-brand class="px-2 pl-3 exo-2 font-weight-normal text-white">
                <h3>
                    Sojourner & Spirit
                </h3>
            </b-navbar-brand>
            <b-navbar-nav>
                <b-nav-item link-classes="open-sans text-white font-weight-bold p-0" class="d-flex"
                            v-if="showBreakpoint">
                    <b-badge variant="dark">
                        <span id="marker-xs" class="d-sm-none">XS</span>
                        <span id="marker-sm" class="d-none d-sm-block d-md-none">SM</span>
                        <span id="marker-md" class="d-none d-md-block d-lg-none">MD</span>
                        <span id="marker-lg" class="d-none d-lg-block d-xl-none">LG</span>
                        <span id="marker-xl" class="d-none d-xl-block">XL</span>
                    </b-badge>
                </b-nav-item>
            </b-navbar-nav>
            <b-navbar-brand class="ml-auto">
                <a href="https://github.com/Xevion/history-of-robotics" target="_blank" v-b-popover.hover.top="'GitHub Source Code'">
                    <font-awesome-icon :icon="['fab', 'github-square']" size="lg" :style="{color: 'white'}"/>
                </a>
            </b-navbar-brand>
        </b-navbar>
        <div id="content" ref="content">
            <b-jumbotron fluid container-fluid="fluid" class="text-dark py-3 px-md-5 px-sm-3">
                <b-row class="px-sm-3 px-md-3 w-100 justify-content-center justify-content-lg-between">
                    <b-col class="d-block d-lg-none py-2 pb-3 py-lg-0" cols="0" sm="7" lg="0" align-self="center">
                        <b-img fluid-grow class="shadow-lg" src="./assets/sojourner.jpg"></b-img>
                    </b-col>
                    <b-col cols="12" lg="8" xl="7" align-self="center">
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
                    <b-col class="d-none d-lg-block" cols="0" lg="4" xl="3" align-self="center">
                        <b-img fluid-grow src="./assets/sojourner.jpg"></b-img>
                    </b-col>
                </b-row>
            </b-jumbotron>

            <b-jumbotron fluid container-fluid="fluid px-0" class="bg-black py-md-5 py-0 px-2 px-md-2 px-lg-3">
                <b-row class="px-3 pl-4 px-md-4 w-100 justify-content-center justify-content-lg-around">
                    <b-col cols="12" lg="6" align-self="top">
                        <h3>Communications</h3>
                        <p class="ml-4 ml-sm-3">
                            Sojourner is unique among the 4 rovers to successfully deploy on Mars in that it required
                            it's lander to stay in communication with Earth. The rover was not equipped with a high gain
                            antenna, which is required in order to communicate with Earth over large distances.
                        </p>
                        <p class="ml-4 ml-sm-3">
                            This limitation forced the rover to stay within a certain range of the lander, and
                            throughout it's lifetime on Mars, it never traveled more than a few dozen feet from the
                            lander.
                        </p>
                        <h3>Tools</h3>
                        <p class="ml-4 ml-sm-3">
                            Sojourner was designed to study the surface of Mars by collecting and analyzing rock
                            samples, taking pictures and more using the following tools:
                        </p>
                        <ul class="ml-3 ml-lg-4">
                            <li class="py-1 pt-2">
                                An <abbr title="Alpha Proton X-ray Spectrometer"><em>APXS</em></abbr> for determining
                                elemental composition of soil, rocks and other materials on the surface of Mars.
                            </li>
                            <li class="py-1">
                                <em>Rover Control Software</em> for coordinating movement, studying terrain features,
                                and viewing the nearby area in 3D space.
                            </li>
                            <li class="py-1">
                                <em>Three cameras</em>, one color, two monochrome. However, the operators primarily
                                used images from the lander's IMP camera system, as it had higher quality on top of
                                having a height advantage over the rover.
                            </li>
                        </ul>
                    </b-col>
                    <b-col cols="12" lg="5" align-h="top" class="w-100 h-100">
                        <h3>Autonomy</h3>
                        <p class="ml-4 ml-sm-3">
                            Sojourner was an important step in Robotics due to the nature of the mission.
                            With such a long distance between Mars and Earth, radio communications took around 14
                            minutes to receive, and then another 14 minutes to send back.
                        </p>
                        <p class="ml-4 ml-sm-3">
                            As such, human telegraphed movements too slow for the mission, and while complete autopilot
                            is impossible for such a complex mission, the rovers, landers, and spacecraft made by NASA
                            had to be programmer with autopilot.
                        </p>
                        <p class="ml-4 ml-sm-3">
                            To solve this problem, Sojourner, along with every rover to land on Mars, is equipped with
                            software dedicated to autonomously moving the rover across the martian surface.
                        </p>
                        <p class="ml-4 ml-sm-3">
                            While Sojourner was comparatively basic in it's software's autonomy, the software was
                            helpful to operators in visualizing and telegraphing instructions across the rocky terrain
                            of Ares Vallis.
                        </p>
                    </b-col>
                </b-row>
            </b-jumbotron>
            <b-jumbotron fluid container-fluid="fluid" class="text-dark py-3 px-md-5 px-sm-3">
                <b-row class="px-sm-3 px-md-3 w-100 justify-content-center justify-content-lg-between">
                    <b-col class="d-block d-lg-none py-2 pb-3 py-lg-0" cols="0" sm="7" lg="0" align-self="center">
                        <b-img fluid-grow class="shadow-lg" src="./assets/spirit.jpg"></b-img>
                    </b-col>
                    <b-col class="d-none d-lg-block py-0 py-lg-4 py-xl-4" cols="0" lg="4" xl="4" align-self="center">
                        <b-img fluid-grow class="shadow-lg" src="./assets/spirit.jpg"></b-img>
                    </b-col>
                    <b-col cols="12" lg="8" xl="7" align-self="center">
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
                    </b-col>
                </b-row>
            </b-jumbotron>
            <b-jumbotron fluid container-fluid="fluid px-0" class="bg-black py-md-5 py-0 px-2 px-md-2 px-lg-3">
                <b-row class="px-3 pl-4 px-md-4 w-100 justify-content-center justify-content-lg-around">
                    <b-col cols="12" lg="6" align-self="top">
                        <h3>Geology</h3>
                        <p class="ml-4 ml-sm-3">
                            Spirit was equipped with all of the tools necessary to complete much more advanced
                            geological
                            inspections and discoveries during it's 90-sol mission. Some tools were made to assist with
                            making smarter choices for what to inspect, and some tools were made to make better
                            analyses.
                        </p>
                        <ul class="ml-3 ml-lg-4">
                            <li class="py-1 pt-2">
                                Several cameras for different situations and identifying different kinds of things.
                                <ul>
                                    <li class="py-1">
                                        A <abbr title="Panoramic Camera">Pancam</abbr> for photographing a wide
                                        (panoramic) color view of the Martian terrain. Produces the highest quality
                                        photos which can be pieced together to create expansive 360 degree collages.
                                    </li>
                                    <li class="py-1">
                                        A <abbr title="Navigational Camera">Navcam</abbr> for quickly transmitting lower
                                        quality monochrome photos at a higher efficiency, typically used in conjunction
                                        with making navigation choices.
                                    </li>
                                    <li class="py-1">
                                        <abbr title="Hazard Avoidance Cameras">Hazcams</abbr>, 2 monochrome cameras,
                                        with 120 degree view angles. Cameras were used generally to support automated
                                        navigation, plan robotic arm movements, and acquire additional imagery of the
                                        martian terrain and landscape close to the rover.
                                    </li>
                                    <li class="py-1">
                                        A <abbr title="Minature Thermal Emission Spectrometer">Mini-TES</abbr> used to
                                        survey rock and soil terrain from a distance, possibly saving scientists
                                        hundreds
                                        of hours on uninteresting experiments.
                                    </li>
                                </ul>
                            </li>
                        </ul>
                    </b-col>
                    <b-col cols="12" lg="5" align-h="top" class="w-100 h-100">
                        <ul>
                            <li>
                                A robotic arm equipped with multiple tools aimed at directly interacting with and
                                analyzing the soil and rock on Mars.
                                <ul>
                                    <li class="py-1">
                                        Just like Sojourner, Spirit was equipped with a
                                        <abbr title="Alpha Proton X-ray Spectrometer"><em>APXS</em></abbr>
                                        for close up analysis of the elemental composition of rocks and soil.
                                    </li>
                                    <li>
                                        A <em>Mössbauer spectrometer</em> used to analyze the composition of
                                        iron-bearing rocks and soil.
                                    </li>
                                    <li>
                                        <em>Rock Abrasion Tool</em> (RAT) for exposing rock underneath the outer layer
                                        (a drill).
                                    </li>
                                </ul>
                            </li>
                        </ul>
                        <h3>Chassis/Body/Frame</h3>
                        <p class="ml-4 ml-sm-3">
                            Each Rover that lands on Mars gets bigger and better - Spirit and Opportunity were the first
                            to show Sojourner this, their dimensions beating Sojourner in each axis by 5 (minimum).
                            Solar panels, wheels, and the tools at their disposal increased too.
                        </p>
                        <!--                        <h3>Communication</h3>-->
                        <!--                        <p class="ml-4 ml-sm-3">-->
                        <!--                            Spirit broke free from the loose tether that Sojourner had previously, leaving it's lander behind using-->
                        <!--                            it's own 3 different radios:-->
                        <!--                        </p>-->
                        <!--                        <ul class="ml-3 ml-lg-4">-->
                        <!--                            <li class="py-1 pt-2">-->
                        <!--                                <em>Ultra-High Frequency Antenna</em>, for relaying information through orbiters around Mars. High throughput.-->
                        <!--                            </li>-->
                        <!--                            <li class="py-1">-->
                        <!--                                <em>X-band High-Gain Antenna</em>, for relaying information directly to Earth.-->
                        <!--                                The antenna rotated itself for a more effective, focused connection. Medium throughput.-->
                        <!--                            </li>-->
                        <!--                            <li class="py-1">-->
                        <!--                                <em>X-band Low-Gain Antenna</em>, used as a robust alternative radio. As a Low-Gain Antenna, it lacked speed,-->
                        <!--                                but made up for it with it's omni-directional capability, not requiring the antenna or rover-->
                        <!--                                to rotate in order for Earth's Deep Space Network to receive it's signals.-->
                        <!--                            </li>-->
                        <!--                        </ul>-->
                    </b-col>
                </b-row>
            </b-jumbotron>
            <b-jumbotron fluid container-fluid="fluid px-0"
                         class="sources text-dark py-3 py-md-4 py-lg-5 mb-0 pb-0 px-2 px-md-2 px-lg-3">
                <h3 class="text-center">
                    Sources
                </h3>
                <b-row class="px-3 pl-4 px-md-4 w-100 justify-content-center justify-content-lg-around">
                    <b-col cols="12" lg="6">
                        <p>
                            "Mars Pathfinder FAQs - Sojourner"
                            <br>
                            <a class="pl-4" href="https://mars.nasa.gov/MPF/rover/faqs_sojourner.html">https://mars.nasa.gov/MPF/rover/faqs_sojourner.html</a>
                        </p>
                        <p>
                            "A Description of the Rover Sojourner"
                            <br>
                            <a class="pl-4" href="https://mars.nasa.gov/MPF/rover/descrip.html">https://mars.nasa.gov/MPF/rover/descrip.html</a>
                        </p>
                        <p>
                            "Mars Pathfinder Instrument Descriptions"
                            <br>
                            <a class="pl-4" href="https://mars.nasa.gov/MPF/mpf/sci_desc.html">https://mars.nasa.gov/MPF/mpf/sci_desc.html</a>
                        </p>
                        <p>
                            "In-situ Exploration and Sample Return: Autonomous Planetary Mobility"
                            <br>
                            <a class="pl-4"
                               href="https://mars.nasa.gov/mer/mission/technology/autonomous-planetary-mobility/">https://mars.nasa.gov/mer/mission/technology/autonomous-planetary-mobility/</a>
                        </p>
                    </b-col>
                    <b-col cols="12" lg="6">
                        <p>
                            "Miniature Thermal Emission Spectrometer (Mini-TES)"
                            <br>
                            <a class="pl-4"
                               href="https://archive.is/20120711083846/http://marsrovers.jpl.nasa.gov/mission/spacecraft_instru_minites.html">
                                https://archive.is/20120711083846/http://marsrovers.jpl.nasa.gov/mission/spacecraft_instru_minites.html
                            </a>
                        </p>
                        <p>
                            "Science Instruments: In-situ Instrumentation"
                            <br>
                            <a class="pl-4"
                               href="https://archive.is/20120710152502/http://marsrovers.jpl.nasa.gov/technology/si_in_situ_instrumentation.html#selection-450.0-465.44">
                                https://archive.is/20120710152502/http://marsrovers.jpl.nasa.gov/technology/si_in_situ_instrumentation.html#selection-450.0-465.44
                            </a>
                        </p>
                        <p>
                            "Hazard Avoidance Camera (Hazcam)"
                            <br>
                            <a class="pl-4"
                               href="https://archive.is/20180808054238/http://an.rsl.wustl.edu/mer/help/Content/About%20the%20mission/MSL/Instruments/MSL%20Hazcam.htm">
                                https://archive.is/20180808054238/http://an.rsl.wustl.edu/mer/help/Content/About%20the%20mission/MSL/Instruments/MSL%20Hazcam.htm
                            </a>
                        </p>
                        <p>
                            "The rover's 'eyes' and other 'senses'"
                            <br>
                            <a class="pl-4"
                               href="https://archive.is/20130217144603/http://marsrover.nasa.gov/mission/spacecraft_rover_eyes.html#selection-650.5-679.37">
                                https://archive.is/20130217144603/http://marsrover.nasa.gov/mission/spacecraft_rover_eyes.html#selection-650.5-679.37
                            </a>
                        </p>
                        <p>
                            "From Sojourner to Curiosity: A Mars Rover Family Portrait"
                            <br>
                            <a class="pl-4"
                               href="https://www.theatlantic.com/technology/archive/2012/08/from-sojourner-to-curiosity-a-mars-rover-family-portrait/260779/">
                                https://www.theatlantic.com/technology/archive/2012/08/from-sojourner-to-curiosity-a-mars-rover-family-portrait/260779/
                            </a>
                        </p>
                    </b-col>
                </b-row>
            </b-jumbotron>
        </div>
    </div>

</template>

<script>
import moment from 'moment';
import './scss/main.scss';

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
