# 低代码规范

# 设计思路

通过 http 请求携带 id 字段，来加载渲染具体活动

## 请求方式

```js
http://172.19.12.140:9082/mallos/web/activity?id='271233344'
id代表具体活动id为'271233344',后端返回数据如下

resData:{
  zoneName:'活动专区'               //专区名称
  template:'1',                   //模版名称
  channel:'pc',                    //PC端
  templateData:{
    pageTitle:'',                 //页面title
    pageIcon:'',                  //页面icon,以url字符串形式
    backgroundColor:{             //背景颜色
     isDefault:false,
     color:'#333'
    },
    isShowTabbar:true,           //显示搜索、导航栏
    isShowSearchBox:true,        //显示搜索框
    logo:{                       //显示logo
      isShow:true,
      url:''
    },
    navigater:[                 //导航名称
      {
        name:'',
        link:''
      }
      ...
    ],
    sliderArea:{                //轮播广告位
      isShow:true,              //是否显示
      showTime:3,               //轮播时长
      sliderResources:[         //轮播资源
        {
          name:'',              //轮播广告名称
          type:'',              //链接类型
          productName:''        //如果类型是商品推广
          url:''                //跳转链接
          imgUrl:''             //图片链接
        }
      ]
    },
    floorAdvertising:
    [
      {
       isShow:true,             //是否显示
       isShowSecond:true,       //显示二级页面
       isShowBrandLabel:true,   //显示商品标签
       name:'',                 //楼层名字
       showNum:{                //商品显示个数
        isAll:false,
        num:4
       }
       productList:[           //商品列表
        {
          name:'',             //商品名称
          imgUrl:'',           //商品图片
          des:'',              //商品简介
          money:'',            //商品价格
          tag:''               //商品标签
        }
       ]
      }
    ]
  }
}
```

## 具体实现

前端通过 http 请求，获取后端返回数据,根据 template 字段和 channel 加载对应模版，通过 channel 判断 pc 还是 h5，在将 templateData 数据渲染到模版上。前端需要增加三个路由页面:

- editActivity 编辑页面，用于通过配置面板来生成模版数据。此页面包含模版组件和配置面板两个组件,通过 template 字段来判断加载不同模版（不同 vue 组件）。配置面板考虑到会有相同配置以及迁移,因此使用一个组件，用 template 字段来判定加载不同配置项，配置项跟上面字段绑定，通过配置项更改模版数据，形成活动页面。

- activity 活动页面，用于展示具体活动页面，该页面只有模版组件，根据活动 id 加载数据渲染模版，生成活动页面
- activitySecondPage 二级页面,通过活动 id,楼层广告位 index，来加载对应数据渲染二级页面，用于加载活动的二级页面。

# 组件封装

以 <font color="#e96900">V</font>+<font color="#e96900">name</font> 命名,比如轮播图组件, 如 <font color="#e96900">VSlider</font>,其封装代码如下:

```
<template>
  <el-carousel :interval="propValue.showTime * 1000">
    <el-carousel-item
      v-for="(item, index) in propValue.sliderResources"
      :key="index"
      style="width: 100%; height: 100%"
    >
      <div style="width: 100%; height: 100%" @click="routeTo(item.imgUrl)">
        <h3>{{ item.name }}</h3>
        <el-image
          style="width: 100%; height: 100%"
          :src="item.imgData"
          fit="fit"
        ></el-image>
      </div>
    </el-carousel-item>
  </el-carousel>
</template>
<script>
export default {
  props: {
    propValue: {
      type: Object,
      default: () => { },
    },
  },
  data() {
    return {
      input: '',
    }
  },
  beforeMount() {

  },
  methods: {
    routeTo(url) {

      window.open(url)
    },
  },
}
</script>
<style>
.el-carousel__container {
  height: 100%;
}
.el-carousel__item h3 {
  color: #176ee0;
  font-size: 18px;
  opacity: 0.75;
  z-index: 1;
  /* line-height: 300px; */
  margin: 0;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>
```

# 组件注册

```js
import Vue from 'vue';

const components = ['VSlider'];

components.forEach((key) => {
  Vue.component(key, () => import(`@/custom-component/${key}`));
});
```

# 组件调用

```js
 <VSlider v-if="resData.templateData.sliderArea.ishow" :propValue="resData.templateData.sliderArea"></VSlider>
```

# 属性面板配置

```js
 <!-- 轮播图 -->

    <el-form-item
      v-if="resData.template==1"
      label="轮播时长"
    >
      <el-select
        v-model="resData.templateData.sliderArea.showTime"
        placeholder="请选择"
      >
        <el-option
          v-for="item in sliderTimes"
          :key="item.value"
          :label="item.label"
          :value="item.value"
        >
        </el-option>
      </el-select>
    </el-form-item>
    <el-form-item
      v-if="resData.template==1"
    >
      <el-card
        v-for="(item, index) in resData.templateData.sliderArea.sliderResources"
        :key="index"
        class="slider_resource mt-40"
      >
        <div class="d-flex">
          <div @click="editImg(index)">
            <el-image
              style="width: 90px; height: 90px"
              :src="item.imgData"
              fit="fit"
            ></el-image>
          </div>

          <div class="d-flex flex-column ai-end ml-30">
            <el-button type="text" @click="toUp(index)">上移</el-button>
            <el-button type="text" @click="toDown(index)">下移</el-button>
            <el-button type="text" @click="delSliderImg(index)">
              删除
            </el-button>
          </div>
        </div>

        <div class="d-flex">
          <span>标题名称:</span>
          <el-input v-model="item.name" placeholder="请输入内容"></el-input>
        </div>
        <div class="d-flex">
          <span>链接类型:</span>
          <el-select v-model="item.type" placeholder="请选择">
            <el-option
              v-for="item in sliderLinkType"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            >
            </el-option>
          </el-select>
        </div>

        <div class="d-flex">
          <span>跳转链接:</span>
          <el-input v-model="item.url" placeholder="请输入内容"></el-input>
        </div>
      </el-card>
      <div
        v-if=" resData.templateData.sliderArea.sliderResources.length < 5"
        class="d-flex jc-center mt-30"
      >
        <el-button type="primary" @click="addSliderImg"> 继续添加 </el-button>
      </div>
    </el-form-item>
  </el-form>
  <el-dialog title="图片" :visible.sync="imgFormVisible" width="500px">
    <el-form :model="imgForm">
      <el-form-item label="图片地址">
        <el-input v-model="imgForm.url" autocomplete="off"></el-input>
      </el-form-item>
      <div>
        <el-button>本地选择</el-button>
        <el-button type="primary" @click="imgFormVisible = false">
          取消
        </el-button>
        <el-button type="primary" @click="imgEditFormConfirm">
          确 定
        </el-button>
      </div>
    </el-form>
  </el-dialog>
```
