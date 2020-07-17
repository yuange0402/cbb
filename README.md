备忘录

<!-- 测试图片 -->
<img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy8xaFJlSGFxYWZhZWljOHAzTHJXZ2VKRVlKblNHTGJKc0JqeWhGZEl3dk9ScEkwNmRpY0ZDVkt1SnB6TDhjam5oZWswSktGM0JKbTNIMG42NXAwZENQeVdRLzY0MA?x-oss-process=image/format,png"> 

1 引入组件的时候要使用相对路径，
2 引入图片的时候使用相对路径，laravel-min会复制图片到public 中
3 去掉nuxt 语法 nuxt-link 之类的，可以保留vue 语法
4 项目目录之间的结构不可以改变，因为使用的是相对路径
6 每一个页面的只都是独立的，每次你给当前html 中新增了一条数据或者给window 新增了一条数据，如果这个时候打开另外的一个页面又会重新加载js 重新定义这些数据，之前的数据都不会保留状态
7 获取到数据，然后在每一个vue文件中解析数据，变成自己需要的格式，然后放到 data 中。

每次进入一个html 都会引入 打包过的 vue.js 文件，这个时候把js加载到内存中，
如果再次打开一个html 又会重新加载 js， 重新开辟内存。
所以每个html 的数据是不互通的。
每一个html 都是一个单独的vue项目。

8 只要有一个组件引入了scss 全局文件，其他的所有的地方都会生效




<!-- 总结：
1 图片，组件 和全局scss 变量都要使用相对路径引入
2 不要使用nuxt 语法，使用vue 语法可以
 -->