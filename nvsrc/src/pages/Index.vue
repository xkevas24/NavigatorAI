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
.navi-card
  width: 100%
  max-width: 250px
  cursor: pointer
  user-select: none
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
          <div class="absolute-bottom-left custom-caption">
            <div class="text-subtitle1">作者：许潇&nbsp;&nbsp;&nbsp;&nbsp;云南大学</div>
          </div>
          <div class="absolute-bottom-right custom-caption">
            <div class="text-subtitle1">最新版本：0.1.20 &nbsp;&nbsp;&nbsp;&nbsp;发布日期：2021年6月30日</div>
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
            <div class="col-md-6">
              <div class="col-md-12">
                <div style="background-color: #66229B;">
                  <p class="text-subtitle2 selection-active" style="text-align: center">MXNet 1.7.0</p>
                </div>
              </div>
              <div class="col-md-12 row" style="text-align: center;">
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
                <div style="background-color: #66229B;">
                  <p class="text-subtitle2 selection-active" style="text-align: center">Python</p>
                </div>
              </div>

              <div class="row col-md-12" style="text-align: center;">
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
                <div style="background-color: #66229B;">
                  <p class="text-subtitle2 selection-active" style="text-align: center">0.1.20</p>
                </div>
              </div>
              <div class="col-md-12" style="margin-top: 16px;">
                <pre style="background-color: #e0e0e0">

  # 方式一：通过nwpm安装（推荐）
  pip3 install nwpm=={{version}}
  nwpm -create {{engine}}_{{cuda}} -platform {{platform}} -version 0.1.20

  # 方式二：直接通过pip安装
  pip3 install nvmx{{cuda}}=={{version}}
                </pre>
              </div>
            </div>
            <div class="col-md-5">
              <div class="row">
                <div class="col">
                  <q-card class="navi-card" style="margin: 0 40px 10px 40px" @click="routeto('/docs')">
                    <q-card-section>
                      <div class="text-h6">框架使用手册</div>
                      <div class="text-subtitle2">Navigator框架使用说明文档</div>
                    </q-card-section>
                  </q-card>
                </div>
                <div class="col">
                  <q-card class="navi-card" style="margin: 0 40px 0 40px" @click="routeto('/bbs')">
                    <q-card-section>
                      <div class="text-h6">社区论坛</div>
                      <div class="text-subtitle2">欢迎提出issue</div>
                    </q-card-section>
                  </q-card>
                </div>
              </div>
              <div class="row">
                <div class="col">
                  <q-card class="navi-card" style="margin: 0 40px 10px 40px" @click="routeto('/pipnwpm')">
                    <q-card-section>
                      <div class="text-h6">包管理器</div>
                      <div class="text-subtitle2">nwpm包管理工具使用文档</div>
                    </q-card-section>
                  </q-card>
                </div>
                <div class="col">
                  <q-card class="navi-card" style="margin: 0 40px 10px 40px" @click="routeto('/nwpm')">
                    <q-card-section>
                      <div class="text-h6">工作包</div>
                      <div class="text-subtitle2">工作包的设计、发布、使用指南</div>
                    </q-card-section>
                  </q-card>
                </div>
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
    },
    routeto(href){
      this.$router.push(href)
    }
  }
}
</script>
