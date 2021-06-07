<template>
  
  <div class="black-bg" v-if="modalState == false">
    <!-- true일경우 렌더링 -->
    <div class="white-bg">
      <img :src="data[index].image" style="width:100%">
      <h4>{{data[index].title}}</h4>
      <p>{{data[index].content}}</p>
      <!-- <input type="text" @input="month = $event.target.value"> -->
      <input type="text" v-model.number="month" v-on:input="$event.target.value = $event.target.value=='' ? 1 : month">
      <p>{{month}}개월 선택함 : {{data[index].price * month}}원</p>
      <button class="close-btn" @click="$emit('closeModal')">X</button>
      <!-- props는 재할당을 하면 안된다 read-only -->
      <!-- v-model 입력한것을 아래의 변수에 저장한다 -->
    </div>
  </div>
</template>

<script>
export default {
    name :'Modal',
    data() {
        return {
            month: 1,
        }
    },
    props : {
        data : Array,
        index : Number,
        modalState: Boolean
    },
}
</script>

<style>

</style>