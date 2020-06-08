<template>
  <section class="section">

    <div class="hero-body">
      <div class="container">
        <h2 class="subtitle text-white text-uppercase">
          HI THERE ! I'M
        </h2>
        <h1 class="title text-white">
          Rajeev Gade
        </h1>
        <h1 class="title text-orange">
          <TextRotator :rotateData="rotateData"/>
        </h1>
      </div>
    </div>

    <div class="tile">
      <div class="tile is-parent" v-for="(val, key) in componentList" :key="key">
        <div class="tile is-child box" @click="showSelectedComponent(val.name)">
          <p class="title">
            <span class="text-white">{{ val.title }}</span> <span class="text-orange">{{ val.subtitle }}</span>
          </p>
        </div>
      </div>
    </div>

    <b-modal :active.sync="isComponentModalActive" full-screen :can-cancel="true">
        <component :is="selectedComponent"/>
    </b-modal>

  </section>
</template>

<script>
import About from '~/components/About'
import Portfolio from '~/components/Portfolio'
import Contact from '~/components/Contact'
import TextRotator from '~/components/TextRotator'

export default {
  name: 'HomePage',

  components: {
    About,
    Portfolio,
    Contact,
    TextRotator
  },

  data() {
    return {
      componentList: [
        { name: 'About', title: 'About', subtitle: 'Me' },
        { name: 'Portfolio', title: 'My', subtitle: 'Portfolio' },
        { name: 'Contact', title: 'Get', subtitle: 'in Touch' }
      ],
      selectedComponent: null,
      isComponentModalActive: false,
      rotateData: ['Creative', 'Tech Savvy', 'Developer']
    }
  },

  methods: {
    showSelectedComponent(comp){
      console.log(comp)
      this.selectedComponent = comp
      this.isComponentModalActive = true
    }
  }
}
</script>

<style>

body{
  background-color: #111;
}

.title{
  text-transform: uppercase;
  text-align: center;
  font-weight: 900;
}

.text-uppercase{
  text-transform: uppercase;
}

.subtitle{
  text-align: center;
}

.box{
  padding-top: 50px;
  padding-bottom: 50px;
  background-color: #222222;
  cursor: pointer;
}

.text-white{
  color: white;
}

.text-orange{
  color: #ffb400;
}

.hero-body{
  margin-bottom: 50px;
}

body{
  height: calc(100vh);
}

.cursor-pointer{
  cursor: pointer;
}
</style>
