<template>
  <div class="recommends">
    <div v-for="item in recommends" :key="item.sort" class="recommends-item">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "RecommendView",
  props:["recommends"]
}
</script>

<style scoped>
  .recommends {
    display: flex;
    justify-content: space-around;
    font-size: 12px;
    padding: 10px 0 20px;
    border-bottom: 8px solid #eee;
  }
  .recommends .recommends-item {
    text-align: center;
  }
  .recommends-item img {
    width: 70px;
    height: 70px;
    margin-bottom: 10px;
  }
</style>