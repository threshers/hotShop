<template>
  <div>
    <swiper :list="demo01_list" v-model="demo01_index" auto></swiper>
    <div>
      <card v-for="(v,index) in 4" :key="index">

        <div slot="header" class="card-padding-top">

        </div>
        <div slot="content" class="card-padding">
          <router-link :to="{ name: 'Home', params: { id: v }}">
            <div style="width: 70%;float:left;">
              <p style="color:#999;font-size:12px;">Posted on January 21, 2015</p>
              <p style="color:#999;font-size:14px;line-height:1.2;">Quisque eget vestibulum nulla. Quisque quis dui quis
                ex ultricies efficitur vitae non felis. Phasellus quis nibh hendrerit..</p>
            </div>
            <div style="width: 30%;float:left">
              <img src="@/assets/test.jpeg" style="width:100%;display: block">
            </div>
          </router-link>
        </div>
        <div slot="footer" class="card-padding">
          <div style="width: 10%;float: left;"><img style="width: 50%" src="@/assets/look.png" alt=""></div>
          <div style="width: 10%;float: left;color:#999;font-size:12px;">45</div>
          <div style="width: 10%;float: left;"></div>
          <div style="width: 10%;float: left;"><img style="width: 50%" src="@/assets/store.png" alt=""></div>
          <div style="width: 10%;float: left;color:#999;font-size:12px;">12</div>
        </div>
      </card>


    </div>


  </div>
</template>

<script>
  import {Swiper, Card} from 'vux'

  export default {
    name: "index",
    components: {
      Swiper,
      Card
    },
    mounted() {
      this.$http.get('http://www.legeek.xyz').then(({data}) => {
        console.log(data)
      })
    },
    data() {
      return {
        demo01_index: 0,
        demo01_list: [{
          url: '/home',
          img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vvsr72j20p00gogo2.jpg',
          title: '送你一朵fua'
        }, {
          url: '/home',
          img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw1k2wj20p00goq7n.jpg',
          title: '送你一辆车'
        }, {
          url: '/home',
          img: 'https://static.vux.li/demo/5.jpg', // 404
          title: '送你一次旅行',
          fallbackImg: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw50iwj20ff0aaaci.jpg'
        }]
      }
    }
  }
</script>

<style scoped lang="less">
  @import '~vux/src/styles/1px.less';

  .card-demo-flex {
    display: flex;
  }

  .card-demo-content01 {
    padding: 10px 0;
  }

  .card-padding {
    padding: 15px;
  }

  .card-padding-top {
    padding: 15px 15px 0px 15px;
  }

  .card-demo-flex > div {
    flex: 1;
    text-align: center;
    font-size: 12px;
  }

  .card-demo-flex span {
    color: #f74c31;
  }
</style>
