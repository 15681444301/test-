<template>
  <view>
    <view class="bg"></view>
    <!-- 搜索开始 -->
    <view class="container_head">
      <view class="container_head_input">
        <input type="text" value="" placeholder="搜索你想要的..." />
        <image
          class="search_icon"
          src="../../static/img/搜索@2x.png"
          mode=""
        ></image>
      </view>
      <image src="../../static/img/分类@3x.png" mode=""></image>
      <image src="../../static/img/消息@2x.png" mode=""></image>
    </view>
    <!-- 搜索结束 -->
    <!-- nav开始 -->
    <view class="container_nav">
      <view
        :class="{ cur: optfor === index }"
        v-for="(item, index) in HomeList"
        :key="index"
        @click="open(index)"
        >{{ item }}</view
      >
    </view>
    <!-- nav结束 -->
    <!-- 图片推荐 -->
    <view class="container_img"
      ><image src="../../static/img/banner@3x.png" mode=""></image
    ></view>
    <!-- 图片推荐 结束-->
    <!-- 今日特卖 -->
    <view class="container_swiper">
      <view class="container_swiper_title">今日特卖</view>
      <view class="container_swiper_subhead">99个惊喜,每天9点更新</view>
      <swiper
        indicator-dots="true"
        autoplay="true"
        class="container_swiper_content"
        interval="3000"
        duration="400"
        circular="true"
      >
        <swiper-item class="swiper_item">
          <view
            class="swiper_item_two"
            v-for="(item, index) in sellList"
            :key="index"
          >
            <image class="item_img" :src="item.img" mode=""></image>
            <view class="item_name">{{ item.product_name }}</view>
            <view class="item_price">￥:{{ item.price }}</view>
          </view>
        </swiper-item>
        <swiper-item class="swiper_item">
          <view
            class="swiper_item_two"
            v-for="(item, index) in sellList"
            :key="index"
          >
            <image class="item_img" :src="item.img" mode=""></image>
            <view class="item_name">{{ item.product_name }}</view>
            <view class="item_price">￥:{{ item.price }}</view>
          </view>
        </swiper-item>
        <swiper-item class="swiper_item">
          <view
            class="swiper_item_two"
            v-for="(item, index) in sellList"
            :key="index"
          >
            <image class="item_img" :src="item.img" mode=""></image>
            <view class="item_name">{{ item.product_name }}</view>
            <view class="item_price">￥:{{ item.price }}</view>
          </view>
        </swiper-item>
      </swiper>
    </view>
    <!-- 今日特卖结束-->
    <!-- 推荐系列 -->
    <view class="container_series">
      <view class="container_series_title">推荐系列</view>
      <view class="container_series_more">
        更多
        <image src="../../static/img/右箭头@2x.png" mode=""></image>
      </view>
    </view>
    <!-- 推荐系列商品展示 -->
    <view class="container_column">
      <view
        class="container_column_item"
        v-for="(item, index) in sellList"
        :key="index"
      >
        <image :src="item.img" mode=""></image>
        <view class="item_name">{{ item.product_name }}</view>
        <view class="item_price">
          ￥:{{ item.price }}
          <text class="item_price_span">/箱</text>
        </view>
      </view>
    </view>
    <!-- 推荐系列商品展示结束 -->
    <!-- 猜你喜欢 -->
    <view class="container_like"
      ><view class="container_like_title">猜·你·喜·欢</view></view
    >
    <view class="container_like_item">
      <view
        class="container_like_you"
        v-for="(item, index) in like"
        :key="index"
      >
        <view class="container_like_img"
          ><image :src="item.img" mode=""></image
        ></view>
        <view class="container_like_name">{{ item.product_name }}</view>
        <view class="container_like_detail">{{ item.detail }}</view>
      </view>
    </view>
    <!-- 猜你喜欢结束 -->
  </view>
</template>

<script>
export default {
  data() {
    return {
      HomeList: ["最新", "美妆", "时尚", "母婴", "零食", "酒水"],
      optfor: 0,
      sellList: [
        {
          product_name: "农夫山泉17.5橙子",
          price: "68",
          img: require("@/static/img/橙子@2x.png"),
        },
        {
          product_name: "智利车厘子",
          price: "68",
          img: require("@/static/img/车厘子商品图@2x.png"),
        },
        {
          product_name: "龍国宴1958",
          price: "68",
          img: require("@/static/img/龙国宴@2x.png"),
        },
      ],
      like: [
        {
          product_name: "智利车厘子JJ级500g",
          detail: "甜蜜酸甜,鲜美多汁,爽脆开胃居家旅行必备",
          img: require("@/static/img/车厘子商品图@3x.png"),
        },
        {
          product_name: "椰青1个装",
          detail: "清甜回甘,椰肉滑嫩，长在你我家门口,爽脆开胃居家旅行必备",
          img: require("@/static/img/椰子商品图@3x.png"),
        },
      ],
    };
  },
  methods: {
    open(index) {
      // console.log(index);
      this.optfor = index;
    },
  },
};
</script>

<style lang="less">
// 猜你喜欢
.container_like {
  height: 60rpx;
  display: flex;
  justify-content: center;
  .container_like_title {
    color: #fcaf22;
  }
}
.container_like_item {
  display: flex;
  height: 400rpx;
  justify-content: space-between;
  margin: 20rpx;
  border-radius: 20rpx;
  .container_like_you {
    width: 330rpx;
    height: 390rpx;
    background-color: #ffffff;
    border-radius: 10rpx;
    .container_like_img {
      width: 330rpx;
      height: 280rpx;
      margin-top: 20rpx;
      image {
        width: 100%;
        height: 100%;
        border-radius: 20rpx;
      }
    }
    .container_like_name {
      font-size: 26rpx;
      font-weight: bold;
    }
    .container_like_detail {
      margin-top: 10rpx;
      font-size: 16rpx;
      color: #a8a9ae;
      overflow: hidden;
      text-overflow: ellipsis;
      display: -webkit-box;
      -webkit-line-clamp: 1;
      -webkit-box-orient: vertical;
    }
  }
}
// 推荐系列商品展示
.container_column {
  height: 300rpx;
  background-color: #ffffff;
  border-radius: 10rpx;
  display: flex;
  justify-content: space-evenly;
  margin: 20rpx;
  .container_column_item {
    width: 170rpx;
    height: 120rpx;
    margin-top: 50rpx;
    image {
      width: 100%;
      height: 100%;
    }
    .item_name {
      font-size: 13rpx;
      white-space: nowrap;
    }
    .item_price {
      font-size: 24rpx;
      font-weight: bold;
      color: red;
      .item_price_span {
        color: #c0c0c0;
        font-weight: 200;
      }
    }
  }
}
// 推荐系列
.container_series {
  display: flex;
  justify-content: space-between;
  margin-top: 30rpx;
  .container_series_title {
    font-size: 28rpx;
    font-weight: bold;
    color: #585858;
    &::after {
      content: "";
      display: block;
      width: 110rpx;
      height: 5rpx;
      background-color: rgba(255, 204, 51, 0.5);
      position: relative;
      top: -8rpx;
      border-radius: 10rpx;
    }
  }
  .container_series_more {
    font-size: 26rpx;
    color: #a6a6a6;
    image {
      margin-left: 10rpx;
      width: 18rpx;
      height: 18rpx;
    }
  }
}
// 推荐系列结束
// 轮播图
.container_swiper {
  height: 400rpx;
  background-color: #ffffff;
  border-radius: 10rpx;
  margin: 20rpx;
  .container_swiper_title {
    color: #585858;
    font-size: 30rpx;
    text-align: center;
    font-weight: 600;
    padding-top: 25rpx;
    color: #000000;
  }
  .container_swiper_subhead {
    font-size: 27rpx;
    text-align: center;
    color: #8e8e8e;
    margin-top: 10rpx;
  }

  .container_swiper_content {
    height: 280rpx;
    display: flex;
    justify-content: space-between;
    .swiper_item {
      display: flex;
      justify-content: space-evenly;
      margin-top: 20rpx;
      .swiper_item_two {
        color: #191919;
        height: 100%;
        .item_img {
          width: 150rpx;
          height: 120rpx;
          image {
            width: 100%;
            height: 100%;
          }
        }
        .item_name {
          font-size: 12rpx;
          white-space: nowrap;
        }
        .item_price {
          font-size: 26rpx;
          font-weight: 600;
          color: red;
        }
      }
    }
  }
}
// 轮播图结束
.container_head {
  display: flex;
  padding: 0 20rpx;
  text-align: center;
  align-items: center;
  background-color: #ffffff;
  .container_head_input {
    display: flex;
    flex: 1;
    position: relative;
    input {
      text-align: center;
      background-color: #eeeeee;
      height: 35rpx;
      color: #000000;
      font-size: 20rpx;
      border-radius: 20rpx;
      position: relative;
      padding: 10rpx;
      flex: 1;
    }
    .search_icon {
      width: 30rpx;
      height: 30rpx;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(calc(-50% - 64rpx), calc(-50% - 2rpx));
    }
  }
  image {
    padding: 5rpx 0 0 20rpx;
    width: 40rpx;
    height: 40rpx;
  }
}
// nav样式
.container_nav {
  height: 80rpx;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  font-size: 27rpx;
  font-weight: 700rpx;
  background-color: #ffffff;
}
.cur {
  font-size: 28rpx;
  color: #3b4144;
  &::after {
    content: "";
    display: block;
    width: 56rpx;
    height: 6rpx;
    background-color: rgba(255, 204, 51, 0.5);
    position: relative;
    top: -8rpx;
    border-radius: 10rpx;
  }
}
// 图片推荐
.container_img {
  image {
    width: 750rpx;
    height: 362rpx;
  }
}
.bg {
  background-color: #f6f6f6;
  position: fixed;
  top: 0;
  height: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}
</style>
