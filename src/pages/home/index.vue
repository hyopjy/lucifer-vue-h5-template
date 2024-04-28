<template>
  <div class="body-d">

    <van-list
      v-model="loading"
      :finished="finished"
      finished-text="没有更多了"
      @load="onLoad"
    >
      <div class="totalItem" v-for="item in list" :key="item.id" @click = "showWorkDetail(item.id)">
        <div class="link">
          <div class="left">
            <div class="fonts"> {{item.name}} </div>
<!--            <div>姓名:{{item.name}}</div>-->
            <div>电话:{{item.tel}}</div>
          </div>
          <div class="right">
            <div class="jindu">工时: {{item.workDay}}/{{item.notWorkDay}}</div>
<!--            <span><van-icon name="arrow" color="#ccc" size="35"/></span>-->
          </div>
        </div>
      </div>
    </van-list>
  </div>
</template>

<script>
import { Toast } from 'vant'
export default {
  name: 'Home',
  data() {
    return {
      list: [
        {
          id: '1',
          code: '001',
          name: '张三222',
          tel: '13000000000',
          workDay: 50,
          notWorkDay: 10
        },
        {
          id: '2',
          code: '002',
          name: '张三333',
          tel: '13000000000',
          workDay: 50,
          notWorkDay: 10
        },
        {
          id: '3',
          code: '002',
          name: '张三333',
          tel: '13000000000',
          workDay: 50,
          notWorkDay: 10
        }
      ],
      loading: false,
      finished: false

    }
  },
  async created() {
  },
  methods: {
    onEdit() {
      Toast('编辑')
    },
    onLoad() {
      this.finished = true
    },
    showWorkDetail(id) {
      const params = { id: id }
      this.$router.push({ path: '/workDate/detail', query: params })
    }
  }
}
</script>

<style lang="scss" scoped>
.body-d {
  margin-top: 50px;
}
.totalItem{
  height: 65px;
  line-height: 65px;
  border-bottom: 1px solid #999;
  margin-top: 10px;
  padding: 10px;
  .link{
    height: 25px;
    line-height: 25px;
    color: #999;
    position: absolute;
    .left{
      float: left;
      .fonts{
        font-size: 20px;
        font-weight:bold;
      }
    }
    .right{
      float: right;
      margin-left: 90px;
    }
  }
}
</style>

