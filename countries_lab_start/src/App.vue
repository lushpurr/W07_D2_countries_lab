<template>
  <div id="app">

    <label for="country_select">Select a Country:</label>
    <select id="country_select" v-model="selectedCountry">
      <option disabled value="">Select a country</option>
      <option v-for="country in countries" :key="country.alpha3code" :value="country">{{country.name}}</option>
    </select>

    <country-detail v-if="selectedCountry" :country="selectedCountry" :neighbouringCountries="neighbouringCountries()">

    </country-detail>

    <button v-if="!favouriteCountries.includes(selectedCountry)" @click="addToFavourites">Add Country to favourites</button>

    <favourite-countries v-if="favouriteCountries.length" :favouriteCountries="favouriteCountries"></favourite-countries>
</div>

</template>

<script>
import CountryDetail from './components/CountryDetail.vue';
import FavouriteListItem from './components/FavouriteListItem.vue';

export default {
  name: 'App',
  data() {
    return {
      countries: [],
      selectedCountry: null,
      favouriteCountries: []
    }
  },
  components: {
    'country-detail': CountryDetail,
    'favourite-countries': FavouriteListItem
  },
    mounted(){
      this.fetchCountry() ;
      

    },
    methods: {
      fetchCountry: function() {
        fetch("https://restcountries.eu/rest/v2/all")
        .then(response => response.json())
        .then(data => this.countries = data)

      },
      addToFavourites: function(){
        this.favouriteCountries.push(this.selectedCountry);
      },
      neighbouringCountries: function(){
        return this.countries.filter((country) => {
          return this.selectedCountry.borders.includes(country.alpha3Code);
        });

      }
      
    }
}
</script>

<style>
li {
  list-style-type:none;
}
.small-flag {
  height: 20px
}



</style>
