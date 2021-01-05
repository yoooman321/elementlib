<script>
export default {
  name: 'Tabs',
  props: {
    value: [Number, String],
    vertical: {
      type: Boolean
    },
    horizontal: {
      type: Boolean
    },
  },
  data () {
    return {
      target: this.value
    }
  },
  methods: {
    test (h) {
      let b = []
      this.$slots.default.forEach(ele => {
        console.log('e: ', ele)
        if (ele.data.attrs.label) {
          b.push(h('div',{
            class: ele.data.staticClass || null,
            on: {
              click: () => this.clickEvent(ele.componentOptions.propsData.name)
            }
          },ele.data.attrs.label))
        } else {
          ele.componentOptions.children.forEach(vnode => {
            if(vnode.data) {
              if(vnode.data.slot === 'label') {
                b.push(h('div',{
                    class: ele.data.staticClass || null,
                    on: {
              click: () => this.clickEvent(ele.componentOptions.propsData.name)
            }
                  },[vnode]))
              }
            }
          })
        }
      })
      return b
    },
    clickEvent(name) {
      console.log('click',name)
      this.target = name
      this.$emit('input', name)
    }
  },
  render (h) {
    const header = h("div", {
      class: {
        "tabs__header": true,
        "tabs__header__horizontal": this.horizontal
      }
    }, this.test(h))
    const panels = h("div", {
      class: "tabs__content"
    }, this.$slots.default)
    return h("div", {
    },[header, panels])
  },
}
</script>
<style>
.tabs__header__horizontal {
  display: flex;
}
</style>