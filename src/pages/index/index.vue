<template>
  <div>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
    >
      <block v-for="img in imgUrls" :key="img">
        <swiper-item>
          <image :src="img" style="width:100% ;height:100%" />
        </swiper-item>
      </block>
    </swiper>
    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
  </i-grid>

  <i-grid i-class="no-border">
    <i-grid-item @click="goType(krid)" v-for="krid in krids" :key="krid" i-class="no-border">
        <i-grid-icon>
            <image :src="krid.image" />
        </i-grid-icon>
        <i-grid-label>{{krid.title}}</i-grid-label>
    </i-grid-item>
  </i-grid>

  <i-grid i-class="no-border">
    <i-grid-item @click="goType(crid)" v-for="crid in crids" :key="crid" i-class="no-border">
        <i-grid-icon>
            <image :src="crid.image" />
        </i-grid-icon>
        <i-grid-label>{{crid.title}}</i-grid-label>
    </i-grid-item>
  </i-grid>

  <i-panel :title="title_name">
    <view style="padding: 15px;">
      <i-card v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
          <view slot="content">{{item.remark}}</view>
          <view slot="footer">{{item.content}}</view>
      </i-card>
    </view>
  </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {

      grids: [
        {title:"定语",image:"/static/images/1.png"},
        {title:"状语",image:"/static/images/2.png"},
        {title:"倒装句",image:"/static/images/3.png"},
        {title:"强调句",image:"/static/images/4.png"}
      ],
      
      krids: [
        {title:"名词",image:"/static/images/5.png"},
        {title:"连词",image:"/static/images/6.png"},
        {title:"动词",image:"/static/images/7.png"},
        {title:"情态动词",image:"/static/images/8.png"}
      ],

      crids: [
        {title:"定语从句",image:"/static/images/9.png"},
        {title:"主语从句",image:"/static/images/10.png"},
        {title:"状语从句",image:"/static/images/11.png"},
        {title:"宾语从句",image:"/static/images/12.png"}
      ],

      imgUrls: [
        'cloud://zqr7-uz0xj.7a71-zqr7-uz0xj-1300800368/1.jpg',
        'cloud://zqr7-uz0xj.7a71-zqr7-uz0xj-1300800368/2.jpg'
      ],
      indicatorDots: true,
      autoplay: false,
      interval: 5000,
      duration: 1000
    }
  },

  methods: {
    goType(type){
      console.log(type)
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({ url })
    }
  },

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
  margin-bottom: 10pt;
}
</style>
