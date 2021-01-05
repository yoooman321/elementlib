<template>
  <div class="hello">
  <tabs v-model="test" class="tabsClass" horizontal>
    <tabs-pane class="className" label="User2" name="test">123</tabs-pane>
    <tabs-pane class="className" label="User3" name="test2">456</tabs-pane>
    <tabs-pane class="className" name="test3"><div slot="label"><img src="https://cdn4.iconfinder.com/data/icons/ionicons/512/icon-image-512.png" /></div><div style="color: red;">789</div></tabs-pane>
  </tabs>
  <div style="height: 200px;"></div>
  <el-tabs v-model="activeName">
    <el-tab-pane name="first"><div slot="label"><img src="https://cdn4.iconfinder.com/data/icons/ionicons/512/icon-image-512.png" /></div>
    RouteUser2</el-tab-pane>
    <el-tab-pane label="Config" name="second">Config2</el-tab-pane>
    <el-tab-pane label="Role" name="third">Role2</el-tab-pane>
    <el-tab-pane label="Task" name="fourth">Task2</el-tab-pane>
  </el-tabs>
  </div>
</template>

<script>
import tabs from './ele/tabs.vue'
import tabsPane from './ele/tabsPane.vue'
import elTabs from './test/tabs.vue'
import elTabPane from './test/tab-pane.vue'
export default {
  data () {
    return {
      activeName: 'first',
      test: 'test'
    }
  },
  methods: {
      // handleClick(tab, event) {
        // console.log(tab, event);
      // }
  },
  components: {
    tabs,
    tabsPane,
    elTabs,
    elTabPane
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  width: 500px;
  margin: 0 auto;
}
</style>
