<template>
<div class="deco">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Reaction Timer🕖</h1>
    <p style="font-style: italic; text-align: center;  margin: -1.4em 0 1.4em 0;">"Be fast as you can"</p>
    <button v-on:click="start" class="button1" :disabled='isresult'>Play</button>
    <MyBlk v-if="isresult" :delay="delay" @end="endGame" />
    <MyRes v-if="showresult" v-bind:score="score" />
</div>
</template>

<script>
import MyBlk from './components/block.vue'
import MyRes from './components/result.vue'
export default {
    name: 'App',
    components: {
        MyBlk,
        MyRes
    },
    data() {
        return {
            isresult: false,
            delay: null,
            score: null,
            showresult: false
        }
    },
    methods: {
        start() {
            this.isresult = true
            this.delay = 2000 * Math.random() + 7000

        },
        endGame(reactime) {
            this.score = reactime //showing result
            this.isresult = false //game end and activating the button
            this.showresult = true
        }

    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500&display=swap');
#app {
    font-family: 'Poppins', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

/* .button1 {
  background-color: white;
  color: black;
  border: 2px solid #4CAF50;
  font-size: 16px;
  padding: 12px 28px;
  border-radius: 4px;
  
}
.button1:hover {
  box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
} */
.button1{
    padding: 8px 28px;
    font-family: 'Poppins', sans-serif;
    border-radius: 4px;
    border: 1px solid #ffffff;
    color: #050C44;
    background-color: #e5e5e5;
    font-size: 0.8em;
}
h1{
    
}
p{
    
}
.deco{
    width: 40%;
    color: white;
    background: #050C44;
    text-align: center;
    margin: 20px auto;
    padding: 100px;
    border-radius: 20px;
    font-size: 1.3em;
    font-weight: lighter;
}
</style>
