<template>
  <div>
    <h3>MyComponent의 아이템 컴포넌트</h3> 
    <button @click="childToParent">클릭됐당</button>
    <input type="text" v-model="childInputData" @keyup.enter="childInput">
  </div>
</template>

<script>
export default {
  name: 'MyComponentItem',
  data: function () {
    return {
      childInputData: null,
    }
  },
  methods: {
    childToParent: function () {
      this.$emit('child-to-parent', '자식이 보낸 나는 데이터다')
    },
    childInput: function () {
      this.$emit('child-input', this.childInputData)
    }
  }
}
</script>

<style>

</style>