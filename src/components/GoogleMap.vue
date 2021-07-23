<template>
<div>
  <div ref="map" style="height:300px;width:500px;"></div>
</div>
</template>

<script>
export default {
  data(){
    return {
      map:'',
      myLatLng:{lat: 35.6581, lng: 139.7017},
    }
  },
  mounted(){
    let script = document.createElement('script');
    script.src = 'https://maps.googleapis.com/maps/api/js?key=AIzaSyDgU8MF5LokSb-S5oCpkAR6BfRXVdHsBg8';
    script.async = true;
    document.head.appendChild(script);

    let timer = setInterval(() => {
      if(window.google){
        clearInterval(timer);
        this.map = new window.google.maps.Map(this.$refs.map, {
            center: this.myLatLng,
            zoom: 14,
            mapTypeControl: false,          
        });
        new window.google.maps.Marker({position:this.myLatLng,map:this.map})
      }
    },500)
  }
}
</script>