<template>
    <div class="header">
            <nuxt-link to='/'>
                <img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png">
            </nuxt-link>
            <div class="headMenu">
                  <nuxt-link v-for="(item,idx) in menuList" :key="idx" :to='item.path' >
                      {{item.title}}
                  </nuxt-link>
            </div>
    </div>
</template>

<script>
export default {
     data(){
          return{
              menuList:[
                  {
                      title:"首页",
                      path:"/"
                  },
                  {
                      title:"产品介绍",
                      path:"/"
                  },
                  {
                      title:"产品案例",
                      path:"/"
                  },
                  {
                      title:"联系我们",
                      path:"/"
                  },
                  
              ]
          }
     }

}
</script>
<style lang="scss" scoped>
    
   .header{
       height:100px;
       display: flex;

       border: 1px solid red;
       img{
           height: 50px;
           width: auto;
           margin-top: 25px;
       }


       .headMenu{
            border: 1px solid darkblue;
            display: flex;
            align-items: center;
            justify-content: center;
       }
   }
</style>

<style>

</style>