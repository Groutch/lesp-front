<template>
  <div class="poi-single">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">{{ poi.title }}</h1>
          <h2 class="subtitle ">{{ poi.longitude }} - {{ poi.latitude }}</h2>
        </div>
      </div>
    </section>
    <section class="poi-content">
      <div class="container">
        <p class="is-size-4 description">{{ poi.description }}</p>
        <div class="poi-images columns is-multiline has-text-centered">
          <div class="column is-one-third">
            <img :src="poi.imgSrc" :alt="poi.title" />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
  export default {
    name: 'POISingle',
    data() {
      return {
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
        ],
        poi: {},
      };
    },
    created() {
      const ID = Number(this.$route.params.id);
      let poi = this.pois.find((poi)=> poi.id === ID);
      this.poi = poi;
    }
  };
</script>
<style lang="scss" scoped>
  .poi-single {
    margin-top: 30px;
  }
  .hero {
    margin-bottom: 70px;
  }
  .poi-images {
    margin-top: 50px;
  }
  .description {
    margin-bottom: 30px;
  }
</style>