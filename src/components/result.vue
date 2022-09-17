<template lang="">
    <div>
        <p class="rank">{{rank}}</p>
        <p class="fontedit">Reaction Time: {{score}} ms</p>
    </div>
</template>
<script>
export default {
    name:'MyRes',
    props:['score'],
    data(){
        return{
            rank: null
        }
    },
    mounted(){
        if(this.score < 200) {
            this.rank= "Ninja Fingers..."
        }
        else if(this.score < 400) {
            this.rank= "Rapid Reflexes...♥"
        }
        else{
            this.rank= "Snail pace...🐌"
        }
    }
}
</script>
<style scoped>
.fontedit{
    font-size: 0.7em;
    font-weight: 400;
    text-align: center;
    margin-top: -1em;
}
.rank{
    padding: 24px 0 0 0 ;
    font-size: 1.2em;
}
</style>