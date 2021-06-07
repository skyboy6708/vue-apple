<template>
<div>
    <img :src="data.image" alt="" class="room-img">
    <h4 @click="$emit('openModal', data.id)" class="card-title">{{data.title}}</h4>
    <p>{{data.price}}원</p>
    <!-- emit 부모한테 이벤트를 방출하다 -->
    <!-- 언제전달 누른애의 정보를 주고 걔만 작동시킬때 -->
</div>
</template>

<script>
export default {
    name: 'Card',
    props : {
        data : Object,
        modalState: Boolean
    }
    
}

</script>

<style>

</style>