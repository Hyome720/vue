<template>
  <div>
    <h1>이건 내가 만든 컴포넌트다</h1>
    <h2>{{ msgComponent }}</h2>
    <h2>{{ dynamicProps }}</h2>
    <MyComponentItem @child-to-parent="parentGetEvent" @child-input="getDynamicData" />
  </div>
</template>

<script>
import MyComponentItem from '@/components/MyComponentItem'

export default {
  name: 'MyComponent',
  components: {
    MyComponentItem,
  },
  props: {
    msgComponent: String,
    dynamicProps: String,
  },
  methods: {
    parentGetEvent: function (childData) {
      console.log(childData)
      console.log('알아 들었다 자이자이자식아')
    },
    getDynamicData: function (childInputData) {
      console.log(`사용자가 입력한 값은 ${childInputData}입니다.`)
    }
  }
}
</script>

<style>

</style>