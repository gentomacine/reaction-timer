<template>
 <div> 
 <P>Reaction Time-{{ score }} MS</P>
  
    <P class = "rank"> {{ rank}} </P> 
    </div>
  
</template>

<script>
export default {
props: ['score'],
data(){
  return{
    rank: null
  }
},
mounted(){
  if (this.score < 2500){
    this.rank = 'Ninja Fingers'
  }
  else if (this.score < 4000){
    this.rank = 'Rapid Reflexes'
  }
  else{
    this.rank = 'Snail Pace...'
  }
}

}
</script>

<style>
.rank{
  font-size: 1.4em;
  color: rgb(30, 146, 59);
  font-weight: bold;
}
</style>