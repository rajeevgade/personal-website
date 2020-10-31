<template>
    <section class="section">
        <section class="hero">
            <div class="hero-body">
                <div class="container">
                    <h1 class="title">
                        <span class="text-white">My</span> <span class="text-orange">Portfolio</span>
                    </h1>
                    <!-- <b-icon icon="card-account-details" /> -->
                </div>
            </div>
        </section>

        <section>
            <b-tabs position="is-centered" class="block" type="is-toggle">
                <b-tab-item label="Programming">
                    <div class="container">
                        <!-- <h4 class="title">
                            <span class="text-white">Programming</span> <span class="text-orange">Projects</span>
                        </h4> -->
                        <div class="columns" v-for="(chunk, value) in getChunkedResults" :key="value">

                            <div class="column is-6" v-for="(val, key) in chunk" :key="key">
                                <div class="container card cursor-pointer box" @click="openExternalUrl(val.url)">
                                    <div class="columns">
                                        <div class="column card-image">
                                            <figure class="image is-4by3">
                                                <img :src="'images/portfolio/' + val.image" :alt="val.title">
                                            </figure>
                                        </div>
                                        <div class="column card-content">
                                            <div class="media">
                                                <!-- <div class="media-left">
                                                    <figure class="image is-48x48">
                                                    <img src="https://bulma.io/images/placeholders/96x96.png" alt="Placeholder image">
                                                    </figure>
                                                </div> -->
                                                <div class="media-content">
                                                    <p class="text-orange" v-html="val.title"></p>
                                                    <!-- <p class="subtitle is-6">@{{ val.client }}</p> -->
                                                </div>
                                            </div>

                                            <div class="content">
                                                <p v-html="val.description" class="text-white"></p>
                                                <p v-if="val.dates">
                                                   <b-icon icon="calendar" size="is-small"></b-icon> <span>{{ val.dates }}</span>
                                                </p>
                                                <div class="tags">
                                                    <span class="tag" v-for="(val, key) in val.skills.split(',')" :key="key">{{ val }}</span>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                        </div>
                    </div>
                </b-tab-item>
                <b-tab-item label="Art">
                    <div class="container">
                        <!-- <h4 class="title">
                            <span class="text-white">Art</span> <span class="text-orange">Projects</span>
                        </h4> -->
                        <div class="columns" v-for="(chunk, value) in getChunkedArtResults" :key="value">

                            <div class="column is-3" v-for="(val, key) in chunk" :key="key">
                                <div class="card cursor-pointer box">
                                    <div class="card-image">
                                        <figure class="image">
                                            <img :src="val.image" :alt="val.title">
                                        </figure>
                                    </div>
                                    <!-- <div class="card-content">
                                        <div class="media">
                                        <div class="media-left">
                                            <figure class="image is-48x48">
                                            <img src="https://bulma.io/images/placeholders/96x96.png" alt="Placeholder image">
                                            </figure>
                                        </div>
                                        <div class="media-content">
                                            <p class="title is-4" v-html="val.title"></p>
                                            <p class="subtitle is-6">@{{ val.client }}</p>
                                        </div>
                                        </div>

                                        <div class="content">
                                            {{ val.description }}
                                            <br>
                                            <time datetime="2016-1-1">{{ val.start_date }} - {{ val.end_date }}</time>
                                        </div>
                                    </div> -->
                                </div>
                            </div>

                        </div>
                    </div>
                </b-tab-item>
                <!-- <b-tab-item label="Sports"></b-tab-item> -->
            </b-tabs>
        </section>

    </section>
</template>

<script>
export default {
    data() {
        return {
            portfolio_items: [
                {
                    title: 'Anime Discovery App', 
                    image: 'anime_535x400.png', 
                    url: 'https://anime-one.now.sh/', 
                    skills: 'Vue.js, Node.js, Firebase, Cordova, Express.js, GraphQL, JavaScript', 
                    client: 'Own', 
                    dates: 'May 2020', 
                    others: [],
                    description: 'Fun Progressive Web App for Anime Lovers'
                },
                {
                    title: 'Online Restaurant Ordering System', 
                    image: 'savemymenu_535x400.png', 
                    url: 'https://www.savemymenu.com/', 
                    skills: 'Laravel, Vue.js, JavaScript, PHP, MySQL, Node.js, Webpack, OAuth, JWT, AWS, Bootstrap', 
                    client: 'Own', 
                    dates: 'May 2019 - Aug 2019', 
                    others: ['savemymenu_2_535x400.png'],
                    description: 'Online Restaurant Ordering System'
                },
                {
                    title: '360&deg; Product Viewer', 
                    image: 'vue-360-viewer.gif', 
                    url: 'https://vue-360.now.sh/', 
                    skills: 'Vue.js, Node.js, Webpack, Babel, HTML5, CSS3, JavaScript', 
                    client: 'Own', 
                    dates: 'Jan 2020', 
                    others: ['vue-360-viewer.png'],
                    description: 'Viewer for 360 Products built on Vue.js'
                },
                {
                    title: 'Website for Dental Hospital', 
                    image: 'dentist_535x400.png', 
                    url: 'https://dental.vercel.app/', 
                    skills: 'Vue.js, Nuxt.js, Bulma, JavaScript', 
                    client: 'Diehl', 
                    dates: 'Aug 2020', 
                    others: [],
                    description: 'Website for Dental Hospital'
                },
                {
                    title: 'Simple Quiz App', 
                    image: 'vue_quiz_app_535x400.png', 
                    url: 'http://rajeevgade.github.io/portfolio/vue-quiz-app/index.html', 
                    skills: 'Vue.js, Node.js, Webpack, Babel, HTML5, CSS3, JavaScript', 
                    client: 'Own', 
                    dates: 'Jan 2020',
                    others: ['vue_quiz_app_2_535x400.png', 'vue_quiz_app_3_535x400.png'],
                    description: 'Quiz app built for fun using vue.js'
                },
                {
                    title: '360&deg; Product Viewer w/ Admin Panel', 
                    image: '360_535x400.png', 
                    url: 'http://www.atpmedia.com/360/', 
                    skills: 'Laravel, PHP, MySQL, OAuth 2.0, jQuery, JavaScript, HTML, CSS', 
                    client: 'ATP', 
                    dates: 'Nov 2018 - Feb 2019',
                    others: [],
                    description: 'Admin Panel for Managing 360&deg; Products'
                },
                {
                    title: 'Desktop Apps', 
                    image: 'electron_535x400.png', 
                    url: null, 
                    skills: 'Node.js, Electron.js, ES6, Bootstrap, HTML, JS, Webpack', 
                    client: 'ATP', 
                    dates: 'Mar 2018 - Dec 2018',
                    others: [],
                    description: 'Desktop Apps built using Electron and Node.js'
                },
                {
                    title: 'Learning Management Systems', 
                    image: '1_535x400.png', 
                    url: null, 
                    skills: 'Laravel, Vue.js, PHP, MySQL, HTML, CSS, jQuery, JavaScript, Bootstrap, Codeigniter, AWS', 
                    client: 'Multiple Clients', 
                    dates: 'Jun 2016 - Present', 
                    others: ['4_535x400.png', '6_535x400.png'],
                    description: 'Learning Management Systems initially built on Codeigniter and upgraded over to use Laravel and Vue'
                },
                {
                    title: '3D Product Viewer w/ Admin Panel', 
                    image: '2_535x400.png', 
                    url: null, 
                    skills: 'Three.js, Knockout.js, Bootstrap, Silex, Codeigniter, Laravel, jQuery, PHP, MySQL, HTML, CSS, Javascript', 
                    client: 'NJATC', 
                    dates: 'Oct 2016 - Jun 2017', 
                    others: [],
                    description: 'Viewer built for displaying 3D Models (.obj and .mtl files)'
                },
                {
                    title: 'Box Entry Layout Activity', 
                    image: '5_535x400.png', 
                    url: null, 
                    skills: 'JavaScript, HTML5, CSS3', 
                    client: 'NJATC', 
                    dates: 'Jun 2017 - Nov 2017', 
                    others: [],
                    description: 'Small Interactive Activity App built on Vanilla JS'
                },
                {
                    title: 'Online Video Upload Form', 
                    image: '7_535x400.png', 
                    url: null, 
                    skills: 'PHP, jQuery, Parsley, HTML, CSS, JavaScript', 
                    client: 'IEC',
                    dates: 'Jun 2017 - Nov 2017', 
                    others: [],
                    description: 'Online Video Upload Form'
                },
                {
                    title: 'Moodle Plugins', 
                    image: 'iec_535x400.png', 
                    url: null, 
                    skills: 'PHP, XMLDB, MySQL, Moodle', 
                    client: 'IEC',
                    dates: 'Aug 2016 - Dec 2016',
                    others: ['iec2_535x400.png'],
                    description: '4 Moodle Plugins'
                },
                {
                    title: 'Packers &amp; Movers', 
                    image: 'everest_535x400.png', 
                    url: 'http://www.everestpackers.com/', 
                    skills: 'HTML, CSS, JS, Bootstrap, jQuery, AWS', 
                    client: 'Everest',
                    dates: 'Oct 2018 - Sep 2018',
                    others: [],
                    description: 'Website for Packers &amp; Movers'
                },
                {
                    title: 'e-Commerce Websites', 
                    image: 'ecommerce_535x400.png', 
                    url: null, 
                    skills: 'PHP, OpenCart, MySQL, HTML, JS, CSS', 
                    client: 'Mulitple Clients',
                    dates: 'Oct 2015 - Sep 2015',
                    others: ['ecommerce2_535x400.png'],
                    description: 'E-Commerce websites built using OpenCart'
                },
            ],
            art_items: [
                {
                    title: 'Captain America', 
                    image: 'https://www.dropbox.com/s/ozg80dtduqk5uwy/IMG_0080.png?raw=1'
                },
                {
                    title: 'Mikasa', 
                    image: 'https://www.dropbox.com/s/cue5pi6t9yjzu91/IMG_0209.png?raw=1'
                },
                {
                    title: 'Sakura', 
                    image: 'https://www.dropbox.com/s/vmsyzxiipaq33pl/IMG_0184.png?raw=1'
                },
                {
                    title: 'Hakuro', 
                    image: 'https://www.dropbox.com/s/cgt84vvyu222v8y/IMG_0133.png?raw=1'
                },
                {
                    title: 'Shinobu', 
                    image: 'https://www.dropbox.com/s/3oqvz2tsh3q8jyz/IMG_0102.png?raw=1'
                },
                {
                    title: 'Tsubaki', 
                    image: 'https://www.dropbox.com/s/f56o8qtrxtnrit9/IMG_0047.png?raw=1'
                },
                {
                    title: 'Zero Two', 
                    image: 'https://www.dropbox.com/s/5tsct3quxcjdivq/IMG_0018.png?raw=1'
                },
                {
                    title: 'Vash', 
                    image: 'https://www.dropbox.com/s/8orbwuba6nag7sf/IMG_0038.png?raw=1'
                },
                {
                    title: 'Higanbana', 
                    image: 'https://www.dropbox.com/s/jjscozxykjob5h5/IMG_0178.png?raw=1'
                },
                {
                    title: 'GitS', 
                    image: 'https://www.dropbox.com/s/wymhktzwptxaeio/IMG_0081.png?raw=1'
                },
                {
                    title: 'Girl w/ Sword', 
                    image: 'https://www.dropbox.com/s/x8udkr2ixmx61q6/IMG_0040.png?raw=1'
                },
                {
                    title: 'Zero Two', 
                    image: 'https://www.dropbox.com/s/y33yho0ezn25kwv/IMG_0064.png?raw=1'
                },
                {
                    title: 'Cute Girl',
                    image: 'https://www.dropbox.com/s/t0f3vbdjqx2lcpr/IMG_0191.png?raw=1'
                },
                {
                    title: 'Pretty Girl', 
                    image: 'https://www.dropbox.com/s/7rz6doqpy956c99/IMG_0039.png?raw=1'
                },
                {
                    title: 'Spidey', 
                    image: 'https://www.dropbox.com/s/ktq42kbjh8rrvyz/C91C8695-C8B0-47D5-9EFD-B50691D18991.jpeg?raw=1'
                }
            ],
            noOfColumns: 2,
            noOfArtColumns: 4,
        }
    },
    computed: {
        chunked(){
            return this.chunk(this.portfolio_items, 4)
        },
        getChunkedResults(array) {
            let arr = this.portfolio_items
            let i = 0
            let arrs = []
            while (i < arr.length) {
                arrs.push(arr.slice(i, i + this.noOfColumns))
                i += this.noOfColumns
            }
            console.log(arrs)
            return arrs
        },
        getChunkedArtResults(array) {
            let arr = this.art_items
            let i = 0
            let arrs = []
            while (i < arr.length) {
                arrs.push(arr.slice(i, i + this.noOfArtColumns))
                i += this.noOfArtColumns
            }
            console.log(arrs)
            return arrs
        },
    },
    methods: {
        openExternalUrl(url){
            if(url){
                window.open(url, '_blank')
            }
        }
    }
}
</script>

<style>
    .modal-content{
        background-color: #111 !important;
    }
    .date{
        color: #aaa;
        font-size: 13px;
    }
    .separator{
        background: #ffb400;
        height: 2px;
        width: 70px;
        margin-bottom: 5px;
        margin-top: 24px;
    }
    
    .tag{
        background-color: #111 !important;
        color: #ffb400 !important;
        border: 1px solid #ffb400;
    }

    .media-content p{
        font-weight: bold;
    }

    .tabs.is-toggle li.is-active a{
        background-color: #ffb400;
        border: none;
        font-weight: bold;
        color: #111;
    }

    .tabs.is-toggle a{
        border-color: #ffb400;
        color: white;
        font-weight: bold;
    }

    .icon{
        vertical-align: sub;
    }
</style>