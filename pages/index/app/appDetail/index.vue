<template>
     <div class="appDetail ybox">
          <topMsg/> 
          <bottomMsg style="margin-top:50px;"/> 
     </div>
</template>
<script>
import topMsg from '../../../../components/index/app/appDetail/topMsg'
import bottomMsg from '../../../../components/index/app/appDetail/bottomMsg' 
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
    @import '../../../../assets/common.scss';
    .appDetail{
        //  border: 8px solid red;
        //  overflow: scroll;
         height: 100%;

         
    }
</style>

<style>

</style>