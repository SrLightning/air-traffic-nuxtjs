<template>
  <div>
    <el-card 
      shadow="always" 
      :body-style="{ padding: '20px' }">
      <div slot="header">
        <h2>Inicio de sesion</h2>
      </div>
      <div>
        <el-row :gutter="24">
          <el-col :span="12">
            <el-form 
              :model="user" 
              ref="form" 
              :rules="rules" 
              :inline="false" 
              size="normal">
              <el-form-item 
                prop="email"
                label="Correo electrónico">
                <el-input 
                  placeholder="Ingrese su correo electrónico"
                  v-model="user.email"/>
              </el-form-item>
              <el-form-item 
                prop="password"
                label="Contraseña">
                <el-input 
                  type="password"
                  show-password
                  placeholder="Ingrese contraseña"
                  v-model="user.password"/>
              </el-form-item>
            </el-form>
            <el-button 
              type="primary" 
              size="default" 
              @click="login">
                Iniciar sesion
            </el-button> <br>
            <el-button 
              type="text" 
              size="default" 
              @click="goToRegister">
              Si no estas registrado, haz click aquí  
            </el-button>
            
            
          </el-col>
        </el-row>        
      </div>
    </el-card>
  </div>
</template>

<script>
export default {
    layout: 'login',
    data() {
      return {
        show: false,
        user: {
          name: '',
          email: '',
          password: '',
        },
        rules: {
          email: ['correo electrónico', { required: true, type: 'email' }],
          password: ['contraseña', { required: true, min: 8, }]
          
        }
      }
    },
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
