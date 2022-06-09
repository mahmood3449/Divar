<template>
  <div class="error">
    <p>متاسفانه برای شهر مورد نظر شما آگهی ثبت نشده است</p>
  </div>
</template>

<script>
export default {
    name:'ErrorPage',
}
</script>

<style lang="scss" scoped>
.error{
        width: 30%;
        height: 20vh;
        border-radius: 5px;
        background: rgba(255, 72, 72, 0.438);
        margin: 100px auto;
        text-align: center;
        color: white;
        p{
          padding: 3rem 2rem;
        }
      }
</style>