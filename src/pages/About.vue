<template>
  <div class="About">
    <article class="layout-padding">
      <div class=ShareThis>
        <h2>Share this App!</h2>
        <img class=qr
             src="~statics/qr.png">
        <a href="https://www.wondrous-badi.today/"
           itemprop="url">
          <span>Open in any web browser:</span>
          <span class=underline>Wondrous-Badi.Today</span>
        </a>
      </div>
      <h1>{{this.title}}</h1>
      <p>This web app is all about the <span itemprop="applicationCategory">Wondrous calendar</span>! It is free to use - share it with others!</p>
      <p>Please send suggestions and comments to
        <span itemprop="author"
              itemscope
              itemtype="http://schema.org/Person">
            <span itemprop="name"><a href="mailto:glen.little@gmail.com">Glen Little</a></span>.</span>
  
        To support ongoing development, please find me at one of these sites:
        <br>
        <a href="https://gratipay.com/Wondrous-Badi-Today/"
           title="Support Glen at Gratipay"
           target="_blank"><img alt="Gratipay"
               src="~statics/gratipay.svg"></a> &nbsp;
        <a href="https://patreon.com/GlenLittle"
           title="Support Glen at Patreon"
           target="_blank"><img alt="patreon"
               src="~statics/patreon.png"></a>
      </p>
      <p>
        <span>Version <span itemprop="softwareVersion">{{version}}</span> ({{versionAge}} - <span class="reload"
              v-on:click="reload">reload now</span>)</span>
      </p>
    </article>
    <iframe class="statusDoc"
            src="https://docs.google.com/document/d/1Q1RtnOocBjW917CHceBbJPSljlDSN5GaZLBp5pu2inA/pub?embedded=false"></iframe>
  </div>
</template>
<style src="./About.vue.css"></style>
<script>
const moment = require('moment-timezone');
var versionInfo = require('../../root/version.json')

export default {
  data() {
    return {
      title: 'About',
      icon: 'info'
    }
  },
  computed: {
    version() {
      return versionInfo.version;
    },
    versionAge() {
      var age = moment(versionInfo.buildDate, "_ MMM D YYYY HH:mm:ss _Z").fromNow();
      return age;
    }
  },
  methods: {
    reload() {
      window.location.reload();
      return false;
    }
  }
}

</script>
