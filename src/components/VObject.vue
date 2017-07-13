<template>
  <div>
    <span>{{ msg }} {{objId}}</span>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'VObject',

  props: {
  },

  data () {
    return {
      msg: 'VObject',
      objId: 0,
      obj: this,
      children: [],
      parent: null
    }
  },

  beforeCreate () {
  },

  created () {
    let obj = {}
    this.objId = this.getNum()
    obj.objId = this.objId
    obj.children = {}
    this.curObj = obj
    console.log('OBJcreated', obj.objId)
    this.$on('CREATE', this.addChild)
    this.$on('CREATE0', this.addChild0)
    this.$on('CREATE1', this.addChild1)
//    this.$parent.$emit('CREATE0', this) // Add to child's created
  },

  beforeMount () {    //  child is added before here
    console.log('OBJbeforeM', this.curObj.objId)
  },

  mounted () {
    console.log('OBJmounted', this.curObj.objId)
  },

  methods: {
    getNum () {
      return Math.floor(Math.random() * Number.MAX_SAFE_INTEGER).toString(16)
    },
    addChild (obj) {
      this.children[obj.objId] = obj
      console.log('ADD', this.objId, obj.objId)
    },
    addChild0 (obj) {
      this.children[obj.objId] = obj
      console.log('ADD0', this.objId, obj.objId)
    },
    addChild1 (obj) {
      this.children[obj.objId] = obj
      console.log('ADD1', this.objId, obj.objId)
    }
  }
}
</script>
