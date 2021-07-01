<style lang="sass" scoped>
.custom-caption
  text-align: center
  padding: 12px
  color: white
.force-22
  height: 22px!important
.selection
  background-color: #E1DDE0
  margin-right: 5px
  cursor: pointer
  color: #616161 !important
.selection-active
  background-color: #66229B
  margin-right: 5px
  cursor: pointer
  color: white
</style>
<template>
  <q-page class="flex">
    <div style="width: 100%">
      <q-carousel
        arrows
        animated
        v-model="slide"
        height="450px"
      >
        <q-carousel-slide name="first" img-src="banner.jpg">
          <div class="absolute-center custom-caption">
            <div class="text-h2">Navigator Framework</div>
            <div class="text-subtitle1">A deep learning framework that encourages people to share.</div>
            <div style="padding-top: 30px">
              <q-btn color="white" text-color="black" label="立刻安装" style="display: none" />
            </div>
          </div>
          <div class="absolute-bottom-right custom-caption">
            <div class="text-subtitle1">最新版本：0.1.20   发布日期：2021年6月30日</div>
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>
    <div id="install" style="width: 100%;margin-top: 50px">
      <div class="row">
        <div class="col-md-2"></div>
        <div class="col-md-8">
          <div class="text-h5">安装 Navigator Framework</div>
          <div class="text-subtitle1" style="margin: 20px 0 20px 0;">请在下方选择您的首选配置，以获得具体的安装方式或命令。</div>
          <div class="row">
            <div class="col-md-1">
              <div class="col-md-12">
                <p class="text-subtitle2 text-grey-6">|内核引擎</p>
              </div>
              <div class="col-md-12">
                <p class="text-subtitle2 text-grey-6">|操作系统</p>
              </div>
              <div class="col-md-12">
                <p class="text-subtitle2 text-grey-6">|开发语言</p>
              </div>
              <div class="col-md-12">
                <p class="text-subtitle2 text-grey-6">|计算平台</p>
              </div>
              <div class="col-md-12">
                <p class="text-subtitle2 text-grey-6">|版本</p>
              </div>
              <div class="col-md-12">
                <p class="text-subtitle2 text-grey-6">|安装命令</p>
              </div>
            </div>
            <div class="col-md-3">
              <div class="col-md-12">
                <div style="background-color: #66229B;width: 500px">
                  <p class="text-subtitle2 selection-active" style="text-align: center">MXNet 1.7.0</p>
                </div>
              </div>
              <div class="col-md-12 row" style="width: 500px;text-align: center;">
                <div class="col force-22 selection-active platform" id="Windows" @click="switch_platform('Windows')">
                  <p class="text-subtitle2">Windows</p>
                </div>
                <div class="col force-22 selection platform" id="Linux" @click="switch_platform('Linux')">
                  <p class="text-subtitle2">Linux</p>
                </div>
                <div class="col force-22 selection platform" id="MacOS" @click="switch_platform('MacOS')">
                  <p class="text-subtitle2">MacOS</p>
                </div>
                <div class="col force-22 selection platform" id="Cloud" @click="switch_platform('Cloud')">
                  <p class="text-subtitle2">Cloud</p>
                </div>
                <div class="col force-22 selection platform" id="Raspberry" @click="switch_platform('Raspberry')">
                  <p class="text-subtitle2">Raspberry</p>
                </div>

              </div>

              <div class="col-md-12" style="margin-top: 16px">
                <div style="background-color: #66229B;width: 500px">
                  <p class="text-subtitle2 selection-active" style="text-align: center">Python</p>
                </div>
              </div>

              <div class="row col-md-12" style="width: 500px;text-align: center;">
                <div class="col force-22 selection-active cuda" @click="switch_cuda('cu102')">
                  <p class="text-subtitle2" id="cu102">CUDA 10.2</p>
                </div>
                <div class="col force-22 selection cuda" @click="switch_cuda('cu111')">
                  <p class="text-subtitle2" id="cu111">CUDA 11.1</p>
                </div>
                <div class="col force-22 selection cuda" @click="switch_cuda('cpu')">
                  <p class="text-subtitle2" id="cpu">CPU Only</p>
                </div>
              </div>

              <div class="col-md-12" style="margin-top: 16px">
                <div style="background-color: #66229B;width: 500px">
                  <p class="text-subtitle2 selection-active" style="text-align: center">0.1.20</p>
                </div>
              </div>
              <div class="col-md-12" style="margin-top: 16px;width: 500px">
                <pre style="background-color: #e0e0e0">

  # 方式一：通过nwpm安装（推荐）
  pip3 install nwpm=={{version}}
  nwpm -create {{engine}}_{{cuda}} -platform {{platform}} -version 0.1.20

  # 方式二：直接通过pip安装
  pip3 install nvmx{{cuda}}=={{version}}
                </pre>
              </div>
            </div>
          </div>
        </div>
        <div class="col-md-2"></div>
      </div>

    </div>
  </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  data(){
    return{
      engine: 'mx170',
      platform: 'Windows',
      language: 'Python',
      cuda: 'cu102',
      version: '0.1.20'
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
    }
  }
}
</script>
