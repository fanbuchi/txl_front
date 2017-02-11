<template>
  <div class="hello">
    <!-- <mt-button>Click Me!</mt-button> -->
    <mt-button @click.native="handleClick">按钮</mt-button>
    <mt-button @click.native="load">加载</mt-button>
    <quill-editor ref="myTextEditor"
                  v-model="content"
                  :config="editorOption">
    </quill-editor>
  </div>
</template>

<script>
import {Toast, Indicator} from 'mint-ui'
import {quillEditor} from 'vue-quill-editor'
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    handleClick () {
      Toast({
        message: 'Hello World!',
        position: 'bottom'
      })
    },
    load () {
      Indicator.open({
        text: '加载中……',
        spinnerType: 'fading-circle'
      })
      setTimeout(() => {
        Indicator.close()
      }, 1000)
    }
  },
  components: {
    'quill-editor': quillEditor
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
