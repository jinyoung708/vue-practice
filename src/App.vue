<template>
  <div id="wrap">
    <Header :leftShow="leftShow" :menus="menus" @toggleMenu="leftShow = !$event;"></Header>

    <div id="content" v-bind:class="{extend: !leftShow}">
      
      <LeftMenu :menus="menus"></LeftMenu>

      <div id="realContent">
        <router-view>
          <div class="container">
              <h2>타이틀1</h2>
              <h3>타이틀2</h3>
              <p>가나다라마바사아</p>
              <div style="height: 1000px;"></div>
          </div>
        </router-view>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/layouts/Header'
import LeftMenu from './components/layouts/LeftMenu'
import $ from 'jquery';

export default {
  name: 'App',
  components: {
    Header,
    LeftMenu,
  },
  data(){
    return {
      menus: [
        {
          name: '메뉴1',
          link: '#'
        },
        {
          name: '메뉴2',
          link: '#'
        },
        {
          name: '메뉴3',
          link: '#'
        },
      ],
      leftShow: true,
    }
  },
  mounted(){
    var progressCurent =100 * $(window).scrollTop() / ($(document).height() - $(window).height());
    $('body').prepend('<div class="page_progressbar_bg horizontal"><div class="page_progressbar"></div></div>');

    $(window).on("scroll", function(){
        pageProgressBar();
    });

    function pageProgressBar(){
        progressCurent =100 * $(window).scrollTop() / ($(document).height() - $(window).height());
        if($('.page_progressbar_bg').hasClass('horizontal')){
                $('.page_progressbar').css('width',progressCurent + "%")
        }else{
                $('.page_progressbar').css('height',progressCurent + "%")
        }
    }
  }
}


</script>

<style lang="scss">
@import "@/assets/scss/common.scss";
</style>
