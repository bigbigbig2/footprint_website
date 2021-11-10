<template>
  <div id="map-wrap" style="height: 100vh">
    <!-- 地图实例 -->
    <l-map style="width: 100%" :zoom="zoom" :center="center" :minZoom="minZoom" :maxZoom="maxZoom">
      <!-- 地图瓦片 -->
      <l-tile-layer :url="url"></l-tile-layer>
    </l-map>
  </div>
</template>

<script>
import { LMap, LTileLayer } from 'vue2-leaflet'
export default {
  components: { LMap, LTileLayer },
  data() {
    return {
      url:
        'http://wprd04.is.autonavi.com/appmaptile?lang=zh_cn&size=1&style=7&x={x}&y={y}&z={z}',
      zoom: 4,
      minZoom: 3,
      maxZoom: 16,
      center: [35.63452, 109.132287] 
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  max-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>