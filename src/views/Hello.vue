<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <vextend></vextend>
    <vextend>
      <vochild></vochild>
    </vextend>
    <vmixin>
      <vechild></vechild>
    </vmixin>
  </div>
</template>

<script>
import Vue from 'vue'
import VObject from '@/components/VObject'
import VExtend from '@/components/VExtend'
import VOChild from '@/components/VOChild'
import VEChild from '@/components/VEChild'
import VMixin from '@/components/VMixin'

Vue.component('vobject', VObject)
Vue.component('vextend', VExtend)
Vue.component('vochild', VOChild)
Vue.component('vechild', VEChild)
Vue.component('vmixin', VMixin)

export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created () {
    console.log('START')
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
