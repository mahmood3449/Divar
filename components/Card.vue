<template>
<nuxt-link :to="{name:'id', params:{id:item.id}}">
  <section class="card">
    <div class="card__img" ><img :src="item.image" alt="">
    <div class="card__noimg"><i class="fa-solid fa-image"></i></div>
    </div>
    <div class="card__desc">
      <p class="card__desc-title">{{item.title}}</p>
      <p class="card__desc-price" v-if="item.price != 0"><span>ریال<span style="visibility: hidden; font-size: 0rem;">i</span></span> {{ convertPrice(item.price) }}</p>
      <p v-else class="card__desc-noprice">توافقی</p>
    </div>
  </section>
  </nuxt-link>
</template>

<script>
export default {
  name: 'CardPage' ,
  props:['item'] , 
  mounted(){
    
  } ,
  methods:{
    convertPrice(price){
     return price.toLocaleString();
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/color/color.scss';
a{
    text-decoration: none;
  }
.card{
  display: grid;
  grid-template-columns: 1fr 1fr;
  height: 25vh;
  border-radius: 5px;
  border: 1px solid $border-color;
  &__img{
    padding: 1rem;
    position: relative;
    img{
      width: 76%;
      height: auto;
      border-radius: 5px;
      position: absolute;
      z-index: 1!important;
    }
  }
  &__noimg{
    width: 76%;
    height: 19vh;
    position: absolute;
    top: 10%;
    border-radius: 5px;
    background: $border-color;
    z-index: 0!important;
    text-align: center;
    i{
      padding-top: 3rem;
      font-size: 2rem;
      color: $font-color;
    }
  }
  &__desc{
    padding: 1rem;
    text-decoration: none;
    &-title{
      font-size: 0.9rem;
      text-align: right;
      font-weight: bolder;
      color: $font-color-titr;
      padding-bottom: 2rem;
    }
    &-price,&-time , &-noprice{
      text-align: right;
      font-size: 0.8rem;
      text-align: right;
      color: $font-color;
      padding-bottom: 0.5rem;
    }
  }
}
</style>