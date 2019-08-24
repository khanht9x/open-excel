<template>
  <div id="wrapper">
    <p>Yunxi Auto</p>
    <div class="version" style="position: fixed; right: 30px; bottom: 30px;">
      <p><small>Version 1.01</small></p>
      <p><small>093.595.0000</small></p>
      <p>{{ path }}</p>
    </div>
  </div>
</template>

<script>
const path = require('path')
const fs = require('fs')
// const app = require('electron').remote.app
export default {
  name: 'open-file',
  data () {
    return {
      pathExcel: '',
      pathCopy: ''
    }
  },
  methods: {
    open (link) {
      this.$electron.shell.openExternal(link)
    }
  },
  mounted () {
    this.pathExcel = path.join(path.dirname(__dirname), '../../extraResources/yunxi-excel.xlsx')
    this.pathCopy = path.join(path.dirname(__dirname), '../../../yunxi-excel.xlsx')
    fs.copyFile(this.pathExcel, this.pathCopy, (err) => {
      if (err) throw err
      console.log('yunxi-excel.xlsx was copied to destination.txt')
    })
  }
}
</script>
