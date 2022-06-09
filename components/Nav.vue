<template>
  <nav class="nav">
      <ul class="nav__menu">
          <li class="nav__menu-btn"><button>ثبت آگهی</button></li>
          <li class="nav__menu-suport"><span>پشتیبانی</span></li>
          <li class="nav__menu-chat"><span>چت <i class="fa-regular fa-comment"></i></span></li>
          <li class="nav__menu-profile"><span>دیوار من <i class="fa-regular fa-user"></i></span></li>
          <li class="nav__menu-search"><input type="text" placeholder="جستجو در میان آگهی ها"><i class="fa-solid fa-magnifying-glass"></i></li>
          <li class="nav__menu-category"><span><i class="fa-solid fa-angle-down"></i> دسته ها</span></li>
          <li class="nav__menu-location" v-on:click="showModal = !showModal"><span>{{ cityfa }} <i class="fa-solid fa-location-dot"></i></span></li>
          <li class="nav__menu-logo"><nuxt-link :to="{name:'index'}">
              <svg width="45" height="50" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M8.38553 14.6173H8.28043C7.89506 14.5647 7.63232 14.1969 7.68487 13.8115C8.15781 10.6936 8.31546 5.71887 8.31546 5.68384C8.35049 5.29848 8.64827 4.98318 9.05115 5.0007C9.43652 5.01821 9.7343 5.33351 9.7343 5.71887C9.7343 5.92907 9.55913 10.8162 9.08619 14.0217C9.03364 14.372 8.73586 14.6173 8.38553 14.6173ZM18.4225 15.9135C18.1247 15.9135 17.8444 15.7208 17.7569 15.423C17.6342 15.0552 17.8444 14.6523 18.2123 14.5472C21.5229 13.4962 21.5754 12.6904 21.593 12.2525C21.628 11.5694 21.1025 10.6936 20.8923 10.3958C20.6646 10.0805 20.7347 9.64257 21.05 9.41485C21.3652 9.18714 21.8032 9.2572 22.0309 9.5725C22.136 9.71263 23.0819 11.0264 22.9943 12.3401C22.9067 13.9341 21.6805 14.915 18.6327 15.896C18.5976 15.896 18.5626 15.9003 18.5276 15.9047C18.4925 15.9091 18.4575 15.9135 18.4225 15.9135ZM8.91102 18.3833C8.70082 18.3833 8.49063 18.2957 8.36801 18.1206C8.12278 17.8228 8.17533 17.3673 8.49063 17.1396C9.92698 16.0011 10.8904 14.9851 11.521 14.0918C11.1706 13.9166 10.8028 13.6538 10.6101 13.2159C10.435 12.8131 10.3299 12.1474 10.9429 11.2541C11.8188 9.95786 12.6946 9.66008 13.0274 9.59002C13.4828 9.50244 13.9207 9.76518 14.0434 10.2031C14.1309 10.5184 14.3411 11.5168 13.7105 13.0408C14.5513 13.0233 15.217 12.7955 15.7249 12.3751C16.7059 11.5869 16.7584 10.2556 16.7584 10.2381C16.7759 9.85277 17.0912 9.55498 17.4766 9.55498C17.8619 9.5725 18.1597 9.8878 18.1597 10.2732C18.1597 10.3432 18.0897 12.2175 16.6358 13.4436C15.7249 14.2144 14.4813 14.5472 12.9748 14.4246C12.2567 15.5281 11.1181 16.8243 9.34893 18.2256C9.2088 18.3307 9.06867 18.3833 8.91102 18.3833ZM12.7121 11.3066C12.5194 11.4643 12.3092 11.692 12.0815 12.0423C11.8538 12.3927 11.8363 12.5853 11.8538 12.6379C11.8888 12.7255 12.064 12.8131 12.2392 12.8831C12.572 12.2175 12.6771 11.692 12.7121 11.3066ZM12.8873 16.2288C12.9048 16.6141 13.2201 16.9119 13.5879 16.9119H13.623C13.6755 16.9119 14.8491 16.8769 16.5307 16.4915C16.9161 16.4039 17.1613 16.0361 17.0737 15.6507C16.9861 15.2654 16.6183 15.0201 16.2329 15.1077C14.6739 15.4405 13.5704 15.4931 13.5529 15.4931C13.1675 15.5106 12.8697 15.8434 12.8873 16.2288ZM1.1337 18.103C1.25631 18.2782 1.48403 18.3833 1.69423 18.3833C1.83436 18.3833 1.97449 18.3483 2.11462 18.2607C6.56381 15.0201 6.73898 10.7811 6.73898 10.606C6.73898 10.2206 6.4412 9.90531 6.05583 9.8878C5.67047 9.87028 5.35517 10.1856 5.33766 10.5709C5.33766 10.7111 5.16249 14.302 1.29135 17.1221C0.976049 17.3498 0.905983 17.7877 1.1337 18.103Z" fill="#A62626"/>
</svg>
          </nuxt-link>
</li>
      </ul>
      <Modal v-if="showModal" v-on:closeModal="closeModal($event)"></Modal>
  </nav>
</template>

<script>
export default {
    name: 'NavPage' ,
    methods:{
        closeModal(close){
            this.showModal = close;
        } 
    } ,
    data(){
        return{
            showModal: false ,
            cityfa: localStorage.getItem('cityfa')?localStorage.getItem('cityfa'):'تهران'
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/color/color.scss';
.nav{
    z-index: 3!important;
    width: 100%;
    height: 9.5vh;
    position: sticky;
    top: 0;
    background: white;
    box-shadow: 0px 1px 4px $font-color;
    // border: 1px solid black;
    &__menu{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 4fr 1fr 1fr 1fr;
        list-style-type: none;
        // li{
        //     // padding: 1rem 0;
        //     border: 1px solid black;
        // }
        &-logo{
            position: relative;
            text-align: center;
            svg{
                // border: 1px solid black;
                margin-top: 0.2rem;
            }
            &::before{
                content: ' ';
                position: absolute;
                top: 1rem;
                left: 1rem;
                height: 4vh;
                border-right: 1px solid $font-color;
            }
        }
        &-location,&-category,&-profile,&-chat,&-suport{
            text-align: center;
            span{
                display: inline-block;
                transition: 700ms;
                margin-top: 0.7rem;
                padding: 0.4rem 1.5rem;
                font-size: 0.9rem;
                color: $font-color;
                border-radius: 5px;
                &:hover{
                    background: $background-color;
                    color: black;
                    cursor: pointer;
                }
            }
        }
        &-search{
            text-align: right;
            padding: 0.3rem;
            position: relative;
          input{
              width: 75%;
              padding: 0.5rem 2.5rem;
              margin-top: 0.3rem;
              text-align: right;
              background: $background-color;
              outline: none;
              border: none;
              border-radius: 5px;
              &::placeholder{
                  color: $font-color;
              }
          }  
          i{
              position: absolute;
              top: 1.3rem;
              right: 1rem;
              color: $font-color;
          }
        }
        &-btn{
            text-align: center;
            button{
                transition: 700ms;
                margin-top: 0.7rem;
                padding: 0.4rem 1.2rem;
                border-radius: 5px;
                color: white;
                border: none;
                background: $btn-color;
                font-weight: bold;
                &:hover{
                    background: #d84343;
                }
            }
        }
        &-chat,&-suport,&-profile{
            text-align: left;
        }
        &-category{
            i{
                padding-right: 0.5rem;
            }
        }
        &-location,&-profile , &-chat{
            i{
                font-size: 1.1rem;
                padding-left: 0.2rem;
            }
        }
    }
}
</style>