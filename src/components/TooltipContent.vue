<template>
  <el-container class="container">
    <el-header height="30px" class="header">
      <div class="title">{{ content.title }}</div>
      <i class="el-icon-close icon" @click="onClose"></i>
    </el-header>
    <el-main class="main">
      <div class="block">
        <span class="display">{{content.description}}</span>
      </div>
      <el-button v-for="action in content.actions" round :key="action.title"
        class="button" @click="onActionClick(action)">
        {{action.title}}</el-button>
    </el-main>
  </el-container>
</template>

<script>
/* eslint-disable no-alert, no-console */
import Vue from "vue";
import {
  Button,
  Container,
  Header,
  Icon,
  Main
} from "element-ui";
import lang from "element-ui/lib/locale/lang/en";
import locale from "element-ui/lib/locale";
locale.use(lang);
Vue.use(Button);
Vue.use(Container);
Vue.use(Header);
Vue.use(Icon);
Vue.use(Main);

export default { 
  name: "TooltipContent",
  methods: {
    onActionClick: function(action) {
      this.$emit("onActionClick", action);
    },
    onClose: function() {
      this.$emit("onClose");
    }
  },
  props: { content: Object },
  data: function() {
    return {

    };
  }

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.header {
  color: #606266;
  line-height: 1;
  padding: 5px 17px 0 15px;
  font-size: 14px;
}

.icon {
  right: 17px;
  position: absolute;
  padding: 5px;
}

.display {
  width: 44px;
  word-break: normal;
}

.title {
  word-break: normal; 
}

.block {
  margin-bottom: 13px;
}

.icon {
  right: 0px;
  position: absolute;
  top: 10px;
}

.icon:hover {
  cursor: pointer;
}

.main {
  font-size: 12px;
  padding: 10px 17px 0 15px;
}

.popover-container {
  height: 100%;
  width: 100%;
}

.button {
  margin-left: 0px !important;
  margin-top: 0px !important;
  font-size: 12px !important;
}

.button+.button {
  margin-top: 10px !important;
}

.button:hover {
  color: #fff !important;
  background: #8300bf !important;
  border: 1px solid #8300bf !important;
}

</style>

<style scoped src="../styles/purple/button.css">
</style>
