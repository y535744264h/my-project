<template>
  <div id="app">
    <p>{{ message }}</p>
    <div v-html="name"></div>
    <label for="r1">修改颜色</label><input type="checkbox" v-model="use" id="r1">
    <br><br>
    <div v-bind:class="{'class1': use}">
      v-bind:class 指令
    </div>
    {{5+5}}<br>
    {{ ok ? 'YES' : 'NO' }}<br>
    {{ message.split('').reverse().join('')}}
    <div v-bind:id="'list-' + id">菜鸟教程</div>
    <p v-if="seen">现在你看到我了</p>
    <pre><a v-bind:href="url">菜鸟教程</a></pre>
    <p>{{ age }}</p>
    <input v-model="age">
    <p>{{ msg }}</p>
    <button v-on:click="reverseMessage">反sss转字符串</button>
    {{ message | capitalize }}
    <!-- 在 v-bind 指令中 -->
  </div>
</template>
<script>
export default {
  el: '#app',
  data () {
    return {
      message: 'Hello Word！',
      name: '<h1>Yanhao</h1>',
      use: false,
      ok: true,
      id: 1,
      seen: true,
      url: 'http://www.runoob.com',
      age: 11
    }
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  },
  filters: {
    capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.toUpperCase() + value.slice(1)
    }
  }
}
</script>

<!--&lt;!&ndash; 样式代码 &ndash;&gt;-->
<!--<style>-->
<!--#app {-->
<!--  font-family: 'Avenir', Helvetica, Arial, sans-serif;-->
<!--  -webkit-font-smoothing: antialiased;-->
<!--  -moz-osx-font-smoothing: grayscale;-->
<!--  text-align: center;-->
<!--  color: #2c3e50;-->
<!--  margin-top: 60px;-->
<!--}-->
<!--</style>-->
