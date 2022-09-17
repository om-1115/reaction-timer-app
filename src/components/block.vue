<template lang="">
    <div class="blockk" v-if="showblock" @click="stoptimer">
        click me
    </div>
    
</template>
<script>
export default {
    name:'MyBlk',
    props:['delay'],
    data(){
        return{
            showblock: false,
            timer:null,
            reactime : 0
        }
    },
    mounted(){
        console.log("mounted")
        setTimeout(() => {
            this.showblock=true
            this.startimer()
        }, this.delay);
    },
    methods:{
        startimer(){
            this.timer= setInterval(() => {
                this.reactime+=10
            }, 10);
        },
        stoptimer(){
            clearInterval(this.timer)
            this.$emit('end' , this.reactime)
            console.log(this.reactime)
        }
    }
}
</script>
<style scoped>
.blockk{
    width: 180px;
    color: #2c3e50;
    background: #ffffff;
    text-align: center;
    margin: 20px auto;
    padding: 100px;
    border-radius: 20px;
    font-size: 1em;
    font-weight: lighter;
}

</style>