<template>
  <gmap-map
    :center="center"
    :zoom="8"
    style="width: 100%; height: 100vh"
  >
    <gmap-marker
      :key="index"
      v-for="(m, index) in markers"
      :position="m.position"
      :title="m.title"
      :clickable="true"
      :draggable="false"
      @click="center=m.position"
    ></gmap-marker>
  </gmap-map>
</template>
<script>
  export default {
    data () {
      return {
        
        center: {lat: this.latitude, lng: this.longitude},
        markers: [{
          position: {lat: this.latitude, lng: this.longitude},
          title: this.title
        }]
      }
    },

    props: {
        latitude: Number,
        longitude: Number,
        title: String
    }
  }
</script>