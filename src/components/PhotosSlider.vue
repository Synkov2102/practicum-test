<template>
  <a-carousel autoplay arrows dots-class="slick-dots slick-thumb">
    <template #customPaging="props">
      <img :src="getData(props.i).photo" />
    </template>
    <a-card v-for="item in 2" :key="item">
      <template #cover>
        <img alt="example" :src="getData(item - 1).photo" />
      </template>
      <a-card-meta :title="getData(item - 1).title">
        <template #description>{{ getData(item - 1).text }}</template>
      </a-card-meta>
    </a-card>
  </a-carousel>
</template>

<script>
import { defineComponent } from 'vue'
const data = [
  {
    photo:
      'https://sun9-12.userapi.com/impf/c636621/v636621684/57b55/nbHLXirsTw0.jpg?size=1620x2160&quality=96&sign=6748cbd098de326857e674b5abbc1edb&type=album',
    title: '2017 год',
    text: 'Я был молод, у меня были солнечные очки и 0 знаний о web-разработке'
  },
  {
    photo:
      'https://sun9-31.userapi.com/impg/fWaYidWxprrXqhkVbD06zgBCcqOUfhQYn2ILDg/27lMnpcAIto.jpg?size=739x991&quality=95&sign=ba3c6fc947f78aa9f67adccc8f98a0c8&type=album',
    title: '2023 год',
    text: 'Успех, слава, деньги, web-разработка, но очков больше нет (Первые 3 пункта под вопросом)'
  }
]

export default defineComponent({
  setup() {
    const getData = (i) => data[i]

    return {
      getData
    }
  }
})
</script>

<style scoped>
:deep(.slick-dots) {
  position: relative;
  height: auto;
}
:deep(.slick-slide div) {
  width: 440px;
  margin: 0 auto;
}

:deep(.slick-arrow) {
  display: none !important;
}
:deep(.slick-thumb) {
  bottom: 0px;
}
:deep(.slick-thumb li) {
  width: 60px;
  height: 45px;
}
:deep(.slick-thumb li img) {
  width: 100%;
  height: 100%;
  filter: grayscale(100%);
  display: block;
}
:deep .slick-thumb li.slick-active img {
  filter: grayscale(0%);
}
</style>
