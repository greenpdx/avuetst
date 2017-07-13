
<script>
// import VObject from './VObject'
import VExtend from './VExtend'

export default {
  name: 'VEChild',
  extends: VExtend,
  components: [VExtend],

  props: {
  },

  data () {
    return {
      msg: 'VEChild',
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
    console.log('VECcreated', obj.objId)
    this.$parent.$emit('CREATE0', this) // adds before child created
  },

  beforeMount () {
    console.log('VECbeforeM', this.curObj.objId)
  },

  mounted () {
    console.log('VECmounted', this.curObj.objId)
  },

  methods: {
  }
}
</script>
