<template>
    <section class="section">
        <section class="hero">
            <div class="hero-body">
                <div class="container">
                    <h1 class="title">
                        <span class="text-white">About</span> <span class="text-orange">Me</span>
                    </h1>
                    <!-- <b-icon icon="card-account-details" /> -->
                </div>
            </div>
        </section>

        <div class="container">
            <div class="tile is-ancestor">
                <div class="tile is-parent">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">Work</span> <span class="text-orange">Experience</span>
                        </p>

                        <p class="separator"></p>
                        <p class="text-white"><b>Digital Media Programmer</b></p>
                        <p class="text-orange">The ATP Group, Inc.</p>
                        <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2016 - present</span></p>
                        
                        <p class="separator"></p>
                        <p class="text-white"><b>Software Developer</b></p>
                        <p class="text-orange">Netxcell Pvt Ltd.</p>
                        <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2013 - 2014</span></p>

                        <p class="separator"></p>
                        <p class="text-white"><b>Web Developer</b></p>
                        <p class="text-orange">Focus I Pvt Ltd.</p>
                        <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2012 - 2013</span></p>

                        <p class="separator"></p>
                        <p class="text-white"><b>Web Developer Intern</b></p>
                        <p class="text-orange">Focus I Pvt Ltd.</p>
                        <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2012 - 2013</span></p>
                    </div>
                </div>
                <div class="tile is-parent">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">My</span> <span class="text-orange">Education</span>
                        </p>

                        <p class="separator"></p>
                        <p class="text-white"><b>Masters in Computer Science</b></p>
                        <p class="text-orange">Northeastern Illinois University</p>
                        <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2014 - 2016</span></p>
                        
                        <p class="separator"></p>
                        <p class="text-white"><b>Bachelors in Computer Science</b></p>
                        <p class="text-orange">Jawaharlal Nehru Technological University</p>
                        <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2008 - 2012</span></p>

                        <p class="separator"></p>
                        <p class="text-white"><b>Board of Intermediary Education</b></p>
                        <p class="text-orange">Narayana Junior College</p>
                        <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2006 - 2008</span></p>
                    </div>
                </div>
                <div class="tile is-parent">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">My</span> <span class="text-orange">Skills</span>
                        </p>

                        <div class="tags">
                            <span class="tag" v-for="(val, key) in skills" :key="key">{{ val }}</span>
                        </div>
                    </div>
                </div>
            </div>

            <div class="tile is-ancestor">
                <div class="tile is-parent">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">5+</span> <span class="text-orange">years</span>
                        </p>
                    </div>
                </div>
                <div class="tile is-parent">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">50+</span> <span class="text-orange">projects</span>
                        </p>
                    </div>
                </div>
                <div class="tile is-parent">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">25+</span> <span class="text-orange">clients</span>
                        </p>
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
            skills: [
                'PHP',
                'Javascript',
                'MySQL',
                'Laravel',
                'Vue.js',
                'React.js',
                'React Native',
                'Nuxt.js',
                'Node.js',
                'Electron.js',
                'Three.js',
                'jQuery',
                'Webpack',
                'NPM',
                'Yarn',
                'Composer',
                'ES 5/6/7',
                'Docker',
                'Quasar',
                'Bootstrap',
                'Bulma',
                'AWS',
                'Firebase',
                'OAuth',
                'Web Services',
                'Apache',
                'IIS',
                'Windows',
                'Linux',
                'Moodle',
                'Joomla',
                'Wordpress',
                'Blackboard',
                'OpenCart',
                'Git',
                'Codeigniter',
                'Silex',
                'HTML 5',
                'CSS 3',
                'XML',
                'JSON',
                'Cordova',
                'PWA'
            ]
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
</style>