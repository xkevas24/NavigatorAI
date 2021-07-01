<style>
.rowico{
  padding-bottom: 15px;
}
</style>
<template>
  <q-layout view="hHh lpR lfr">
    <q-header style="height: 60px">
      <q-toolbar>
        <q-icon name="explore" size="40px" color="accent"></q-icon>

        <q-toolbar-title>
          Navigator
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer style="height: 300px">
      <div class="row" style="padding-top: 20px">
        <div class="col-md-2"></div>
        <div class="col-md-8">
          <div class="row">
            <div class="col-md-4">
              <div class="row rowico">
                <q-img src="apache_incubator_logo.png" width="200px"></q-img>
              </div>
              <div class="row rowico">
                <q-img src="ynu.png" width="200px"></q-img>
              </div>
              <div class="row rowico">
                <q-img src="mxnet_logo.png" width="140px"></q-img>
              </div>
              <div class="row rowico">
                <q-img src="quasar.png" width="200px"></q-img>
              </div>



            </div>
            <div class="col-md-8">

              <p>Since the Navigator Fframework uses Apache MXNet as the kernel, this framework can be used as a community-optimized version of MXNet.</p>

              <p>"Copyright © 2021, Ownership of the unique design in the Navigator Framework is owned by author -  Alan Hsu and Yunnan University."</p>

              <p>Apache MXNet is an effort undergoing incubation at The Apache Software Foundation (ASF), sponsored by the Apache Incubator. Incubation is required of all newly accepted projects until a further review indicates that the infrastructure, communications, and decision making process have stabilized in a manner consistent with other successful ASF projects. While incubation status is not necessarily a reflection of the completeness or stability of the code, it does indicate that the project has yet to be fully endorsed by the ASF.</p>

              <p>"Copyright © 2017-2018, The Apache Software Foundation Apache MXNet, MXNet, Apache, the Apache feather, and the Apache MXNet project logo are either registered trademarks or trademarks of the Apache Software Foundation."</p>

            </div>
          </div>
        </div>
        <div class="col-md-2"></div>
      </div>
    </q-footer>

  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',
  setup () {
    return {

    }
  }
})
</script>
