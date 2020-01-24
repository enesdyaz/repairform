<template>
<div>
  <div>
      <v-switch style='margin-left: 30px;' v-model="model1" label='power'></v-switch>
  </div>
  <div v-show="model1">
     
      <v-chip v-for="item in items" :key="item" :value='item'>{{item}}</v-chip>
    
  </div>
</div>
</template>

<script>
export default {
    data(){
        return{
        model1:false,
        items: ['a','b','c']
        }
    },

    computed: {
        doubleNum(){
            return this.num*2 
        }
    }
}
</script>

<style>

</style>