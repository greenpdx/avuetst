
<script>
import VObject from './VObject'
// import VExtend from './VExtend'

export default {
  name: 'VOChild',
  extends: VObject,
  components: [VObject],

  props: {
  },

  data () {
    return {
      msg: 'VOChild',
      vochild: 1
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
    console.log('VOCcreated', obj.objId)
    this.$parent.$emit('CREATE0', this) // adds before child created
  },

  beforeMount () {
    console.log('VOCbeforeM', this.curObj.objId)
  },

  mounted () {
    console.log('VOCmounted', this.curObj.objId)
  },

  methods: {
  }
}
</script>
