<template>
  <div id="app">
    <img src="./assets/logo.png" />
    <div>
      Search:
      <input type="text" v-model="query" placeholder="Search" />
    </div>
    <br />
    <div v-html="highlight()"></div>
  </div>
</template>

<script>
export default {
  name: 'app',

  // inialise 2 variables, query = user input, content = text to be searched.
  data () {
    return {
      query: '',
      content:
        'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse dignissim leo massa, sed aliquet leo posuere ut. Curabitur malesuada accumsan erat, id varius eros tincidunt quis. Vivamus lobortis, odio at fermentum efficitur, risus est tincidunt nisl, eget condimentum tellus dui vitae nibh. Donec id lorem condimentum, porttitor augue in, fermentum leo. Morbi condimentum, nunc ut malesuada placerat, sem nulla condimentum purus, iaculis tristique metus diam lobortis enim. Suspendisse potenti. Quisque urna magna, porta eget erat ac, pharetra vehicula erat. Suspendisse sed nisi ex.'
    }
  },

  // If query empty just return.
  // function highlight() is called if query is not empty.
  // It highlights query text by changing the class around the matching text.
  methods: {
    highlight () {
      if (!this.query) {
        return this.content
      }
      return this.content.replace(new RegExp(this.query, 'gi'), (match) => {
        return '<span class="highlightText">' + match + '</span>'
      })
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.highlightText {
  background: rgb(72, 255, 0);
}
</style>
