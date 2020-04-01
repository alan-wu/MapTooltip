<template>
  <div v-bind:style="position">
    <el-popover trigger="manual" width="243" :disabled="disabled" :value="visible"
      :placement="placement" visible-arrow="true" ref="popover" :popper-options="options">
      <TooltipContent :content="content" @onActionClick="onActionClick"
      @onClose="onClose"/>
      <div slot="reference"></div>
    </el-popover>
  </div>
</template>

<script>
/* eslint-disable no-alert, no-console */
import Vue from "vue";
import {
  Popover,
} from "element-ui";
import lang from "element-ui/lib/locale/lang/en";
import locale from "element-ui/lib/locale";
import TooltipContent from "./TooltipContent.vue";
locale.use(lang);
Vue.use(Popover);

export default {
  name: "TooltipVuer",
  components: {
    TooltipContent
  },
  methods: {
    onActionClick: function(action) {
      this.$emit("onActionClick", action);
    },
    onClose: function() {
      this.$emit("onClose");
    }
  },
  props: {
    options: {
      type: Object,
      default: function() {
        return {};
      } 
    },
    placement: String, 
    visible: Boolean,
    content: Object,
    position: Object
  },
  data: function() {
    return {
      disabled: false
    };
  }

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

