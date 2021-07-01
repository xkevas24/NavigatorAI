<template>
  <q-page class="flex">
    <div style="width: 100%">
      <iframe src="https://github.com/xkevas24/NavigatorMX" style="width: 100%;height: 1080px">
      </iframe>
    </div>

  </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  data(){
    return{

    }
  },
  setup () {
    return {
      slide: ref('first'),
    }
  },
  methods:{
    switch_platform(keyword){
      var plat = document.getElementsByClassName('platform')
      var platlen = document.getElementsByClassName('platform').length
      for(var i=0; i<platlen; i++){
        plat[i].classList = "col force-22 selection platform"
      }
      document.getElementById(keyword).classList = "col force-22 selection-active platform"
      this.platform = keyword
    },
    switch_cuda(keyword){
      var plat = document.getElementsByClassName('cuda')
      var platlen = document.getElementsByClassName('cuda').length
      for(var i=0; i<platlen; i++){
        plat[i].classList = "col force-22 selection cuda"
      }
      document.getElementById(keyword).classList = "col force-22 selection-active cuda"
      this.cuda = keyword
    },
    routeto(href){
      this.$router.push(href)
    }
  }
}
</script>
