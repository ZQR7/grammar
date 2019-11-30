<template>
  <div>
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
        {title:"定语从句",image:"/static/images/5.png"},
        {title:"主语从句",image:"/static/images/6.png"},
        {title:"状语从句",image:"/static/images/7.png"},
        {title:"宾语从句",image:"/static/images/8.png"}
      ],

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
