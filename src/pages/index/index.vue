<template>
  <div id="index">
    <div class="page">
      <div class="page__bd">
        <div class="weui-tab">
          <div class="weui-navbar">
            <block v-for="(item,index) in tabs" :key="index">
              <div :id="index" :class="['weui-navbar__item', activeIndex === index ? 'weui-bar__item_on' : '']"
                @click="tabClick">
                <div class="weui-navbar__title">{{item}}</div>
              </div>
            </block>
          </div>
          <div class="weui-tab__panel">
            <div class="weui-tab__content" :hidden="activeIndex != 0">
              <div class="weui-article">
                <div class="weui-article__h1">大标题</div>
                <div class="weui-article__section">
                  <div class="weui-article__title">章标题</div>
                  <div class="weui-article__section">
                    <div class="weui-article__h3">1.1 节标题</div>
                    <div class="weui-article__p">
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut
                      labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
                      nisi ut aliquip ex ea commodo consequat.
                    </div>
                    <div class="weui-article__p">
                      <image class="weui-article__img" :src="imgSrc" mode="aspectFit"
                        style="height: 180px" />
                      <image class="weui-article__img" :src="imgSrc" mode="aspectFit"
                        style="height: 180px" />
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="weui-tab__content" :hidden="activeIndex != 1">选项二的内容</div>
            <div class="weui-tab__content" :hidden="activeIndex != 2">
              <div class="page">
                <div class="page__bd page__bd_spacing">
                  <div class="weui-flex">
                    <div class="weui-flex__item">
                      <div class="placeholder">理财</div>
                    </div>
                    <div class="weui-flex__item">
                      <div class="placeholder">轻音乐</div>
                    </div>
                  </div>
                  <div class="weui-flex">
                    <div class="weui-flex__item">
                      <div class="placeholder">手账</div>
                    </div>
                    <div class="weui-flex__item">
                      <div class="placeholder">古典音乐</div>
                    </div>
                    <div class="weui-flex__item">
                      <div class="placeholder">电影</div>
                    </div>
                  </div>
                  <div class="weui-flex">
                    <div class="weui-flex__item">
                      <div class="placeholder">手机摄影</div>
                    </div>
                    <div class="weui-flex__item">
                      <div class="placeholder">健身</div>
                    </div>
                    <div class="weui-flex__item">
                      <div class="placeholder">设计</div>
                    </div>
                    <div class="weui-flex__item">
                      <div class="placeholder">饮食</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
    <div class="weui-footer weui-footer_fixed-bottom">
      <div class="weui-footer__text">Copyright © 2008-2018 海边的小溪鱼</div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        tabs: ['轻芒', '深度阅读', '兴趣'],
        activeIndex: 0,
        imgSrc:require("../../../static/images/a.jpg")
      }
    },
    methods: {
      tabClick(e) {
        console.log(e);
        this.activeIndex = Number(e.currentTarget.id);
      }
    },
    created() {}
  }

</script>

<style lang="less">
  // @import "./reset.css";
  page,
  .page,
  .page__bd {
    height: 100%;
  }

  .page__bd {
    padding-bottom: 0;
  }

  .weui-navbar__title {
    display: block;
  }

  .weui-tab__content {
    padding-top: 60px;
    text-align: center;
  }

  .placeholder {
    margin: 5px;
    padding: 0 10px;
    text-align: center;
    background-color: #ebebeb;
    height: 2.3em;
    line-height: 2.3em;
    color: #cfcfcf;
  }

</style>
