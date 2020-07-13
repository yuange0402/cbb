<template>
     <div class="appDetail">
          <topMsg/> 
          <bottomMsg/> 
     </div>
</template>
<script>
import topMsg from '@/components/index/app/appDetail/topMsg'
import bottomMsg from '@/components/index/app/appDetail/bottomMsg' 
export default {
    data(){
        return{

        }
    },
    methods:{},
    components:{
        topMsg,
        bottomMsg
    }

}
</script>
<style lang="scss" scoped>
    .appDetail{
         border: 8px solid red;
         overflow: scroll;
         height: 100%;
    }
</style>

<style>

</style>