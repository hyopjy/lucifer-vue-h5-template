<template>
  <div class="body-d">
    <div>
      <van-grid :gutter="10">
        <van-grid-item v-for="value in 12" :key="value" icon="photo-o" text="文字11"/>
      </van-grid>
    </div>
    <div>
      <van-button icon="plus" type="primary" @click="fillWorkData()">工时填报</van-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WorkDetail',
  data() {
    return {
      id: null
    }
  },
  methods: {
    fillWorkData() {
      const params = { id: this.id }
      this.$router.push({ path: '/workDate/fill', query: params })
    }
  },
  async mounted() {
    const id = this.$route.query.id
    this.id = id
    console.log(id)
  }
}
</script>

<style scoped lang="scss">
.body-d {
  margin-top: 50px;
}
</style>
