<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
  import axios from '@/ajax';
  import URL from '@/urlConfig';
  export default {
    name: 'HelloWorld',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },
    methods: {
      /*
       * params: 无
       * return: 无
       * function: 测试用
       * */
      getTestData: function () {
        let ths = this;
        axios.get(URL.test2)
          .then(function (response) {
            let data = response.data;
            console.log('d', data);
          })
          .catch(function (error) {
            console.error(error);
          });
      }
    },
    mounted: function () {
      this.getTestData();
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  h1{
    font-weight: normal;
    color: #42b983;
  }
</style>
