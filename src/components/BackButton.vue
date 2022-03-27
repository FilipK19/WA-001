<template>
  <div class="back-button">
    <span class="go-back">
        <button @click="goBack">go back</button>
    </span>
  </div>
</template>

<script>
export default {
    methods: {
        goBack(){
            return this.$router.go(-1)
        }
    }
}
</script>
