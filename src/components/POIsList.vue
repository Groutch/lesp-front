<template>
  <div class="pois container">
    <h2 class="subtitle is-3">Liste des P.O.I.</h2>
    <div class="columns is-multiline">
      <div v-for="poi in pois" :poi="poi" :key="poi.id" class="column is-one-quarter">
        <router-link :to="'/poi/' + poi.id">
          <POICard :poi='poi'/>
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
  import POICard from '@/components/POICard';
  export default {
    name: 'POIsList',
    components: {
      POICard,
    },
    data() {
      return {
        poi: {},
        pois: [
          {
            id: 1,
            longitude: '0,999999',
            latitude: '0,888888',
            title: 'POI1',
            description: 'desc 1',
            imgSrc: 'https://placekitten.com/500/500',
          },
          {
            id: 2,
            longitude: '0,777777',
            latitude: '0,666666',
            title: 'POI2',
            description: 'desc 2',
            imgSrc: 'https://placekitten.com/500/500',
          },
          {
            id: 3,
            longitude: '0,555555',
            latitude: '0,444444',
            title: 'POI3',
            description: 'desc 3',
            imgSrc: 'https://placekitten.com/500/500',
          },
        ]
      }
    }
  };
</script>
<style lang="scss" scoped>
  .pois {
    margin-top: 100px;
    text-align: center;
  }
</style>