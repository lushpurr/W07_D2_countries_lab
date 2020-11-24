<template lang="html">
  <div id="neighbouring_countries">
  <h3>Neighbouring Countries</h3>
    <ul id="neighbouring_countries">
      <li v-for="neighbouringCountry in neighbouringCountries">
        <span> {{neighbouringCountry.name}} </span>
        <img class="med-flag" :src="neighbouringCountry.flag"/>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'neighbouring-countries',
  props: ['neighbouringCountries']
}
</script>

<style lang="css" scoped>
li {
  display:flex;
  flex-flow: row;
}

.med-flag {
  height: 40px
}
</style>
