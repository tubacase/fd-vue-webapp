<template>
  <v-ons-page>
    <custom-toolbar v-bind="toolbarInfo"></custom-toolbar>
    <div class="bold-title">Freedomotic Vue Dashboard 0.0.1</div>
    <div class="info-text">
      <div class="bold-title">Main contributors</div>
      <div>Mauro Cicolella</div>
      <div>P3trur0</div>
      <a href="https://github.com/freedomotic/fd-vue-webapp/graphs/contributors" target="_blank">GitHub contributors</a>
    </div>
    <div class="info-text">
      <div class="bold-title">{{$t('connection_parameters')}}</div>
    </div>
    <div class="info-text">
      <div class="bold-title">{{$t('freedomotic_information')}}</div>
    </div>
    <div class="info-text">
      <div class="bold-title">{{$t('credits')}}</div>
    </div>
    <div>{{systemInfo}}</div>
  </v-ons-page>
</template>

<script>
export default {
  props: ['pageStack', 'setOptions'],

  data () {
    return {}
  },
  mounted () {
    this.$store.dispatch('getSystemInfo')
  },
  computed: {
    systemInfo () {
      return this.$store.state.systemInfo
    }
  }
}
</script>
<style>
    .bold-title {
         font-weight: bolder; 
         font-size: larger;
     }
     
     .info-text {
        justify-content: space-around;
        width: inherit;
        height: inherit;
        display: flex;
        margin: auto;
        flex-direction: column;
        text-align: center;
    }
</style>
