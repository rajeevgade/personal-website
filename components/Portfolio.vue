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

        <div class="container">
            <div class="columns" v-for="(chunk, value) in getChunkedResults" :key="value">

                <div class="column is-3" v-for="(val, key) in chunk" :key="key">
                    <div class="card cursor-pointer">
                        <div class="card-image">
                            <figure class="image is-4by3">
                                <img :src="'images/portfolio/' + val.image" :alt="val.title">
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
    </section>
</template>

<script>
export default {
    data() {
        return {
            portfolio_items: [
                {
                    title: 'Online Restaurant Ordering System', 
                    image: 'savemymenu_535x400.png', 
                    url: 'https://www.savemymenu.com/', 
                    skills: 'Laravel, Vue.js, JavaScript, PHP, MySQL, Node.js, Composer, Webpack, Babel, OAuth 2.0, JWT, Blade, AWS, Bootstrap', 
                    client: 'Own', 
                    start_date: 'May 2019', 
                    end_date: 'Ongoing',
                    others: ['savemymenu_2_535x400.png'],
                    description: 'Online Restaurant Ordering System built using Laravel and Vue'
                },
                {
                    title: '360&deg; Product Viewer', 
                    image: 'vue-360-viewer.gif', 
                    url: 'http://rajeevgade.github.io/portfolio/vue-360-viewer/index.html', 
                    skills: 'Vue.js, JavaScript, Node.js, NPM, Webpack, Babel, HTML5, CSS3', 
                    client: 'Own', 
                    start_date: 'Jan 2020', 
                    end_date: '',
                    others: ['vue-360-viewer.png'],
                    description: 'Viewer for 360 Products built on Vue.js'
                },
                {
                    title: 'Simple Quiz App', 
                    image: 'vue_quiz_app_535x400.png', 
                    url: 'http://rajeevgade.github.io/portfolio/vue-quiz-app/index.html', 
                    skills: 'Vue.js, JavaScript, Node.js, NPM, Webpack, Babel, HTML5, CSS3', 
                    client: 'Own', 
                    start_date: 'Jan 2020', 
                    end_date: '',
                    others: ['vue_quiz_app_2_535x400.png', 'vue_quiz_app_3_535x400.png'],
                    description: 'Quiz app built for fun using vue.js'
                },
                {
                    title: '360&deg; Product Viewer w/ Admin Panel', 
                    image: '360_535x400.png', 
                    url: 'http://www.atpmedia.com/360/', 
                    skills: 'Laravel, PHP, MySQL, OAuth 2.0, jQuery, JS, HTML, CSS', 
                    client: 'ATP', 
                    start_date: 'Nov 2018', 
                    end_date: 'Feb 2019',
                    others: [],
                    description: 'Admin Panel for Managing 360&deg; Products'
                },
                {
                    title: 'Doc Conversion Tools', 
                    image: 'electron_535x400.png', 
                    url: 'http://www.atpmedia.com/360/', 
                    skills: 'Node.js, Electron.js, ES6, Bootstrap, HTML, JS, Webpack', 
                    client: 'ATP', 
                    start_date: 'Mar 2018', 
                    end_date: 'Dec 2018',
                    others: [],
                    description: 'Desktop Apps built using Electron and Node'
                },
                {
                    title: 'Learning Management Systems', 
                    image: '1_535x400.png', 
                    url: '#', 
                    skills: 'Laravel, Vue.js, PHP, MySQL, HTML, CSS, jQuery, Ajax, JavaScript, XML, JSON, Bootstrap, Codeigniter, Apache, Analytics', 
                    client: 'Multiple Clients', 
                    start_date: 'Jun 2016', 
                    end_date: 'Present',
                    others: ['4_535x400.png', '6_535x400.png'],
                    description: 'Learning Management Systems initially built on Codeigniter and upgraded over to use Laravel and Vue'
                },
                {
                    title: '3D Product Viewer w/ Admin Panel', 
                    image: '2_535x400.png', 
                    url: '#', 
                    skills: 'Three JS, Knockout JS, Bootstrap, Silex, Codeigniter, PHP, MySQL, HTML, CSS, JS', 
                    client: 'NJATC', 
                    start_date: 'Oct 2016', 
                    end_date: 'Jun 2017',
                    others: [],
                    description: 'Viewer built for displaying 3D Models (.obj and .mtl files)'
                },
                {
                    title: 'Box Entry Layout Activity', 
                    image: '5_535x400.png', 
                    url: '#', 
                    skills: 'JavaScript, HTML5, CSS3', 
                    client: 'NJATC', 
                    start_date: 'Jun 2017', 
                    end_date: 'Nov 2017',
                    others: [],
                    description: 'Viewer built for displaying 3D Models (.obj and .mtl files)'
                },
                {
                    title: 'Online Video Testimonial Submission', 
                    image: '7_535x400.png', 
                    url: '#', 
                    skills: 'PHP, jQuery, Parsley, HTML, CSS and JavaScript', 
                    client: 'IEC',
                    start_date: 'Jun 2017', 
                    end_date: 'Nov 2017',
                    others: [],
                    description: 'Online Video Testimonial Submission'
                },
                {
                    title: 'Moodle Plugins', 
                    image: 'iec_535x400.png', 
                    url: '#', 
                    skills: 'PHP, XMLDB, MySQL, Moodle', 
                    client: 'IEC',
                    start_date: 'Aug 2016', 
                    end_date: 'Dec 2016',
                    others: ['iec2_535x400.png'],
                    description: 'Developed 4 Moodle Plugins'
                },
                {
                    title: 'Packers &amp; Movers', 
                    image: 'iec_535x400.png', 
                    url: 'http://www.everestpackers.com/', 
                    skills: 'HTML, CSS, JS, Bootstrap, jQuery, AWS', 
                    client: 'Everest',
                    start_date: 'Oct 2018', 
                    end_date: 'Sep 2018',
                    others: [],
                    description: 'Website for Packers &amp; Movers'
                },
                {
                    title: 'e-Commerce Websites', 
                    image: 'ecommerce_535x400.png', 
                    url: '#', 
                    skills: 'PHP, OpenCart, MySQL, HTMl, JS, CSS', 
                    client: 'Mulitple Clients',
                    start_date: 'Oct 2015', 
                    end_date: 'Sep 2015',
                    others: ['ecommerce2_535x400.png'],
                    description: 'E-Commerce websites built using OpenCart'
                },
            ],
            noOfColumns: 4,
        }
    },
    computed: {
        chunked(){
            return this.chunk(this.portfolio_items, 4)
        },
        getChunkedResults() {
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
    },
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
</style>