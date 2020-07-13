<template>
     <div class="test">
          <div class="box" @dragend="dragend" draggable = "true">88888</div>
          <div class="boxW" @drop="drop" ></div>
     </div>
</template>

<script>
export default {
    methods:{
        mousemove(e){
             console.log(e,"鼠标移动=====")
        },
        dragend(e){
            console.log(e,"拖动行为结束==========")
        }, 
        drop(e){
             e.preventDefault();
             console.log(e,"监听到有box放入")
        }

    }

}
</script>
<style lang="scss" scoped>
    .box{
         border: 1px solid red;
         width: 100px;
         height: 100px;
    }

    .boxW{
         border: 1px solid darkblue;
         position: absolute;
         bottom: 0;
         right: 0;
         width: 500px;
         height: 500px;
    }
</style>
<style lang="scss" scoped>
  
</style>

<style>

</style>