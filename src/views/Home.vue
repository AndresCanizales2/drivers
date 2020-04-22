<template>
  <div>
    <h1>Google Maps Demo</h1>
 
    <GmapMap :center="center" :map-type-id="mapTypeId" :zoom="18">
     <GmapCustomMarker  :marker="ayuda"  >
      <img src="https://www.stickpng.com/assets/images/58482acecef1014c0b5e4a1e.png" />
      </GmapCustomMarker>  

           <GmapCustomMarker  :marker="center"  >
      <img src="https://www.stickpng.com/assets/images/58482acecef1014c0b5e4a1e.png" />
      </GmapCustomMarker>  
     <GmapMarker
        v-for="(item, index) in markers"
        :key="index"
        :position="item.position"
        @click="center = item.position"
      />
  
    </GmapMap>
  </div>
</template>

<script>

import GmapCustomMarker from 'vue2-gmap-custom-marker';

export default {
  data() {
    return {

      ayuda : {lat: 4.140481, lng: -73.611540 },
      center: { lat: 4.140781, lng: -73.611540 },
      mapTypeId: "terrain",
     markers: [
        { position: { lat: -0.48585, lng: 117.1466 } },
      ]
    };
  },
   components: {
     GmapCustomMarker,
  } 
};
</script>

<style  scoped>
.vue-map-container {
  height: 450px;
  max-width: 992px;
  width: 100%;
}

img{
  width: 40px;
  height: 40px;
}
</style>