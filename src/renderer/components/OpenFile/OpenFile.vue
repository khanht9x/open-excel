<template>
  <div id="wrapper">
    <p>Yunxi Auto</p>
    <div class="version" style="position: fixed; right: 30px; bottom: 30px;">
      <p><small>Version 1.01</small></p>
      <p><small>093.595.0000</small></p>
    </div>
  </div>
</template>

<script>
const path = require('path')
export default {
  name: 'open-file',
  data () {
    return {
    }
  },
  methods: {
    open (link) {
      this.$electron.shell.openExternal(link)
    }
  },
  mounted () {
    this.path = path.join(path.dirname(__dirname), '../../extraResources/yunxi-excel.xlsx')
    this.open(this.path)
  }
}
</script>
