<template>
  <div>
    <el-row :gutter="24">
      <el-col>
        <p>
          Index...
        </p>
      </el-col>
    </el-row>
    
  </div>
</template>

<script>
export default {
    data() {
      return {
        show: false,
      }
    },
    layout: 'default',
    methods: {
      login() {
        console.log(this.user)  
      },
      goToRegister() {
        this.$router.push({ path: '/register' })
      }
    },
}
</script>
