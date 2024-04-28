<template>
  <div class="body-d">
    <van-calendar
      title="工时填报"
      :poppable="false"
      :show-confirm="false"
      :style="{ height: '600px' }"
    />
  </div>
</template>

<script>
export default {
  name: 'FillWorkDate',
  data() {
    return {
      id: null
    }
  },
  methods: {
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
