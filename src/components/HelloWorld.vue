<template>
  <div class="hello">
    <h2>{{time}}</h2>
  
    <ul>
      <li>
        <a href="javacript:void(0)" v-on:click="startButton">
          开始
        </a>
      </li>
      <li>
        <a href="javacript:void(0)" v-on:click="stopButton">
          停止
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
let it;
let second = 0;
let mis =0;
export default {
  name: 'HelloWorld',
  data () {
    return {
      time:'0:000',
    }
  },
  methods: {
    startButton: function () {
    console.log('startButton')
      var me = this;
      
      it = setInterval(
        function(){
          mis++;
          if(mis == 999)
          {
            second++;
            mis=0;
          }
          me.time = second +':' + mis;
        }, 1)
    },
    stopButton: function() 
    {
      console.log('stopButton')
      clearInterval(it)
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
