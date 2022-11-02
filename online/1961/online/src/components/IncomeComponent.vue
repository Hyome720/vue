<template>
  <div>
    <p>
      연봉 입력 (만원) :
     <input type="text" v-model="incomeInput" @keyup.enter="createIncome">
    </p>

    <p>
      세액감면액 (만원) :
      <input type="text">
    </p>
    <hr>
    <h2>종합소득금액 : {{ }} 만원</h2>
    <h2>종합소득공제 : {{ }} 만원</h2>
    <h2>과세표준 : {{ }} 만원</h2> 
    <hr>
  </div>
</template>

<script> 
export default {
  name: 'IncomeComponent',
  data: function () {
    return {
      incomeInput: null,
    }
  },
  methods: {
    createIncome: function () {
      this.$emit('create-income', this.incomeInput)
      this.incomeInput = null
    }
  }
}
</script>

<style>

</style>