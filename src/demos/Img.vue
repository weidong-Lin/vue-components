<template>
  <layout class="demos img-demos">
    <x-header slot="header">
      <div slot="title">XImg</div>
    </x-header>
    <x-body slot="body" class="scrollbox">
      <x-img class="my-img" @click="clickHandler" @load="loadHandler" src="http://assets.bittyos.com/images/swiper/01.jpg" :loading="true"/>
      <p>新华社北京5月27日电 中共中央政治局5月26日下午就推动形成绿色发展方式和生活方式进行第四十一次集体学习。中共中央总书记习近平在主持学习时强调，推动形成绿色发展方式和生活方式是贯彻新发展理念的必然要求，必须把生态文明建设摆在全局工作的突出地位，坚持节约资源和保护环境的基本国策，坚持节约优先、保护优先、自然恢复为主的方针，形成节约资源和保护环境的空间格局、产业结构、生产方式、生活方式，努力实现经济社会发展和生态环境保护协同共进，为人民群众创造良好生产生活环境。

学习开始时，播放了有关生态环境保护的专题片。随后，何立峰、姜大明、陈吉宁、陈政高、陈雷同志先后发言，他们结合本部门工作实际谈了对推进生态文明建设、推动绿色发展、加强环境保护等方面的体会和意见。</p>
      <x-img class="my-img" @click="clickHandler" @load="loadHandler" src="http://assets.bittyos.com/images/swiper/02.jpg" :loading="true"/>
      <p>新华社北京5月27日电 中共中央政治局5月26日下午就推动形成绿色发展方式和生活方式进行第四十一次集体学习。中共中央总书记习近平在主持学习时强调，推动形成绿色发展方式和生活方式是贯彻新发展理念的必然要求，必须把生态文明建设摆在全局工作的突出地位，坚持节约资源和保护环境的基本国策，坚持节约优先、保护优先、自然恢复为主的方针，形成节约资源和保护环境的空间格局、产业结构、生产方式、生活方式，努力实现经济社会发展和生态环境保护协同共进，为人民群众创造良好生产生活环境。

学习开始时，播放了有关生态环境保护的专题片。随后，何立峰、姜大明、陈吉宁、陈政高、陈雷同志先后发言，他们结合本部门工作实际谈了对推进生态文明建设、推动绿色发展、加强环境保护等方面的体会和意见。</p>
      
      <x-img class="my-img" @click="clickHandler" @load="loadHandler" src="http://assets.bittyos.com/images/swiper/03.jpg" :loading="true"/>
            <p>新华社北京5月27日电 中共中央政治局5月26日下午就推动形成绿色发展方式和生活方式进行第四十一次集体学习。中共中央总书记习近平在主持学习时强调，推动形成绿色发展方式和生活方式是贯彻新发展理念的必然要求，必须把生态文明建设摆在全局工作的突出地位，坚持节约资源和保护环境的基本国策，坚持节约优先、保护优先、自然恢复为主的方针，形成节约资源和保护环境的空间格局、产业结构、生产方式、生活方式，努力实现经济社会发展和生态环境保护协同共进，为人民群众创造良好生产生活环境。

学习开始时，播放了有关生态环境保护的专题片。随后，何立峰、姜大明、陈吉宁、陈政高、陈雷同志先后发言，他们结合本部门工作实际谈了对推进生态文明建设、推动绿色发展、加强环境保护等方面的体会和意见。</p>
      
      <x-img class="my-img" @click="clickHandler" @load="loadHandler" src="http://assets.bittyos.com/images/swiper/04.jpg" :loading="true"/>
            <p>新华社北京5月27日电 中共中央政治局5月26日下午就推动形成绿色发展方式和生活方式进行第四十一次集体学习。中共中央总书记习近平在主持学习时强调，推动形成绿色发展方式和生活方式是贯彻新发展理念的必然要求，必须把生态文明建设摆在全局工作的突出地位，坚持节约资源和保护环境的基本国策，坚持节约优先、保护优先、自然恢复为主的方针，形成节约资源和保护环境的空间格局、产业结构、生产方式、生活方式，努力实现经济社会发展和生态环境保护协同共进，为人民群众创造良好生产生活环境。

学习开始时，播放了有关生态环境保护的专题片。随后，何立峰、姜大明、陈吉宁、陈政高、陈雷同志先后发言，他们结合本部门工作实际谈了对推进生态文明建设、推动绿色发展、加强环境保护等方面的体会和意见。</p>
      
      <x-img class="my-img" @click="clickHandler" @load="loadHandler" src="http://assets.bittyos.com/images/swiper/05.jpg" :loading="true"/>
    </x-body>
    <preview :list="images" ref="preview"/>
  </layout>
</template>

<script>
import {
  Layout,
  XHeader,
  XBody,
  XImg,
  Preview
} from 'components'

let windowWidth = window.innerWidth

export default {
  components: {
    Layout,
    XHeader,
    XBody,
    XImg,
    Preview
  },
  data () {
    return {
      images: []
    }
  },
  methods: {
    loadHandler (e) {
      let img = e.target
      let natural = {
        w: img.naturalWidth,
        h: img.naturalHeight
      }
      let item = {
        src: img.src,
        w: natural.w > windowWidth ? windowWidth : img.w,
        h: natural.w > windowWidth ? natural.h / natural.w * windowWidth : img.h
      }
      this.images.push(item)
    },
    clickHandler (e) {
      let index = 0
      this.images.forEach((item, i) => {
        if (item.src === e.target.src) {
          index = i
        }
      })
      this.$refs.preview.open(index)
    }
  }
}
</script>

<style lang="scss">
  .img-demos img{
    display:block;
    width:100%;
  }
  .img-demos p{
    line-height:1.8;
    padding:10px;
    color:#666;
  }
  .img-demos .my-img{
    min-height:100px;
  }
</style>
