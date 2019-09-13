<template lang="pug">
#app
  img(src='./assets/logo.png')
  h1 
    b-alert(show dismissible variant='success')  Hello {{ title }}! 
  select(v-model="selectedCountry")
    option(v-for="country in contries" v-bind:value="country.value") {{ country.name}}
  spinner(v-show="loading")
  ul
    //- li(v-for="artist in artists") {{ artist.name }}
    artist(v-for="artist in artists" v-bind:artist="artist" v-bind:key="artists.mbid")
</template>


<script>
import Artist from "./components/Artist.vue";
import Spinner from "./components/Spinner.vue";
import getArtists from "./api";

export default {
  name: "app",
  data() {
    return {
      title: "Miausic",
      artists: [],
      contries: [
        { name: "Spain", value: "Spain" },
        { name: "Germany", value: "Germany" },
        { name: 'Colombia', value: 'Colombia' },
        { name: "Mexico", value: "Mexico" },
      ],
      selectedCountry: "Spain",
      loading: true
    }
  },
  components: {
    Artist: Artist,
    Spinner : Spinner
  },
  methods: {
    refreshArtists() {
      const self = this;
      this.loading = true;
      this.artists = []
      getArtists(this.selectedCountry).then(function(artists) {
        self.loading = false
        self.artists = artists
      });
    }
  },
  mounted: function () {
    this.refreshArtists()
  },
  watch: {
    selectedCountry: function () {
      this.refreshArtists()
    }
  }
};
</script>

<style lang="stylus">
#app 
	font-family 'Avenir', Helvetica, Arial, sans-serif
	-webkit-font-smoothing antialiased
	-moz-osx-font-smoothing grayscale
	text-align center
	color #42b983
	background-color #00003e
h1, h2 
	font-weight normal
ul 
	list-style-type none
	padding 0
li 
	display inline-block
	margin 0 10px
a 
	color #42b983
</style>
