
<script>
import VObject from './VObject'

export default {
  name: 'VMixin',
  mixins: [VObject],
  components: [VObject],

  props: {
  },

  data () {
    return {
      msg: 'VMixin',
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
    console.log('MXNcreated', this.curObj.objId)
    this.$parent.$emit('CREATE0', this) // adds before child created
  },

  beforeMount () {
    console.log('MXNbeforeM', this.curObj.objId)
  },

  mounted () {
    console.log('MXNmounted', this.curObj.objId)
  },

  methods: {
  }
}
</script>
