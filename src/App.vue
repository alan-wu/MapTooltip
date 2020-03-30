<template>
  <div id="app">
    <TooltipVuer :placement="placement" :visible="visible" :content="content" 
      :position="tooltipStyle" @onActionClick="onActionClick" @onClose="onClose"/>
  </div>
</template>

<script>
/* eslint-disable no-alert, no-console */
import TooltipVuer from './components/TooltipVuer.vue'

export default {
  name: 'app',
  methods: {
    onActionClick: function(action) {
      console.log("action", action)
    },
    onClose: function() {
      console.log("close");
    }
  },
  data: function(){
    return {
      content: {
        title: "Test",
        placement: "bottom",
        description: "Description", 
        actions: [
          {
            title: "View 3D scaffold",
            url: "placeholder"
          },
          {
            title: "View plot",
            url: "placeholder"
          }
        ]
      },
      visible: false,
      tooltipStyle: {
        top: "200px",
        left: "100px",
        position: "absolute"
      }
    }
  },
  components: {
    TooltipVuer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height:100%;
  width: 100%;
  position:absolute;
}

body {
  margin: 0px;
}

</style>
