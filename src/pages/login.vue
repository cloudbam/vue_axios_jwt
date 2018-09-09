<template>
  <div class="hello">
    <div>{{msg}}</div>
    <div @click="login">login</div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
        loginForm: {
          name: "liu",
          password: '1234'
        },
    }
  },
  methods:{
    login(){
      this.$http.post('/api/login', this.loginForm).then(res => {
          localStorage.setItem('token', res)
          location.replace('/index')
           console.log(res);
           
      })
      
      
    }
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
