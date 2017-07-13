
<script>
import VObject from './VObject'

export default {
  name: 'VExtend',

  extends: VObject,

  components: [VObject],

  props: {
  },

  data () {
    return {
      msg: 'VExtend',
      extend: 1
    }
  },

  beforeCreate () {

  },

  created () {
    let obj = {}
    this.objId = this.getNum()
    obj.objId = this.objId
    obj.children = []
    this.curObj = obj
    console.log('EXTcreated', this.curObj.objId)
    this.$parent.$emit('CREATE', this) // adds before child created
  },

  beforeMount () {
    console.log('EXTbeforeM', this.curObj.objId)
  },

  mounted () {
    console.log('EXTmounted', this.curObj.objId)
  },

  methods: {
    addChild0 (obj) {
      this.children[obj.objId] = obj
      console.log('EADD0', this.objId, obj.objId)
    }
  }
}
</script>
