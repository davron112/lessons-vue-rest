<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <ul style="text-align: center">
      <li v-for="(lesson, index) in lessons" :key="index">{{ lesson.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      default:'--'
    }
  },
  created() {
    axios
        .get('http://student.lc/api/lessons')
        .then(response => {
          this.lessons = response.data
        })
        .catch(error => {
          console.log(error)
        })
  },
  data() {
    return {
      text: '-',
      lessons: []
    }
  },
  watch: {
    text(value) {
      console.log(value, '-- O\'zgarish')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
