<template>
    <section class="section">
        <section class="hero">
            <div class="hero-body">
                <div class="container">
                    <h1 class="title">
                        <span class="text-white">Get</span> <span class="text-orange">In Touch</span>
                    </h1>
                    <!-- <b-icon icon="card-account-details" /> -->
                </div>
            </div>
        </section>

        <div class="container">
            <div class="tile is-ancestor">
                <div class="tile is-parent is-vertical">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">Email</span> <span class="text-orange">ID</span>
                        </p>
                        <p class="text-orange subtitle">rajeevgade@gmail.com</p>
                        <!-- <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2016 - present</span></p> -->
                    </div>
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">Skype</span> <span class="text-orange">ID</span>
                        </p>
                        <p class="text-orange subtitle">gade.rajeev.reddy</p>
                        <!-- <p><span class="date"><b-icon size="is-small" icon="calendar-blank" /> 2016 - present</span></p> -->
                    </div>
                </div>
                <div class="tile is-parent">
                    <div class="tile is-child box">
                        <p class="title">
                            <span class="text-white">Social</span> <span class="text-orange">Profiles</span>
                        </p>
                        <div class="title">
                            <template v-for="(social, k) in social_profiles">
                                <a :href="social.url" :key="k" target="_blank">
                                    <b-icon
                                        pack="fab"
                                        :icon="social.icon"
                                        size="is-large"
                                        :type="social.type">
                                    </b-icon>
                                </a>
                            </template>
                        </div>
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
            social_profiles: [
                { title: 'Facebook', url: 'https://facebook.com/rajeevgade', icon: 'facebook', type: 'is-primary' },
                { title: 'Github', url: 'https://github.com/rajeevgade', icon: 'github', type: 'is-light' },
                { title: 'LinkedIn', url: 'https://www.linkedin.com/in/rajeev-reddy-gade-6b59371b?trk=nav_responsive_tab_profile', icon: 'linkedin', type: 'is-info' },
                { title: 'Google Plus', url: 'https://plus.google.com/u/0/+RajeevReddyG/', icon: 'google-plus', type: 'is-danger' },
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