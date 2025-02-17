<script setup lang="ts">
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

let loading = ref(false)

const form = ref<any>({
  email: '',
  password: '',
  confirmPassword: '',
})

function signUp(val: any) {
    loading.value = true
    
  console.log(val)
}

function onError(error: any) {
  console.log(error)
}
</script>

<template>
  <div class="view-wrapper">
    <a-row>
      <a-col :xs="24" :sm="18" :md="12" :lg="10" :xxl="8">
        <a-card>
          <a-form
            name="sign-up-form"
            layout="vertical"
            :wrapper-col="{ span: 8 }"
            :model="form"
            @finish="signUp"
            @finishFailed="onError"
          >
            <a-form-item
              label="Email Address"
              name="email"
              :rules="[{ required: true, message: 'Email address is required!' }]"
            >
              <a-input v-model:value="form.email" />
            </a-form-item>

            <a-form-item
              label="Password"
              name="password"
              :rules="[{ required: true, message: 'Password is required!' }]"
            >
              <a-input-password v-model:value="form.password" />
            </a-form-item>

            <a-form-item
              label="Confirm password"
              name="confirmPassword"
              :rules="[{ required: true, message: 'Please re-enter your password!' }]"
            >
              <a-input-password v-model:value="form.confirmPassword" />
            </a-form-item>

            <a-form-item>
              <a-button type="primary" html-type="submit" :loading="loading">Create Account</a-button>
            </a-form-item>

            <a-form-item>
              <p>
                Already have an account?
                <RouterLink to="/sign-in">
                    Login
                </RouterLink>
              </p>
            </a-form-item>
          </a-form>
        </a-card>
      </a-col>
    </a-row>
  </div>
</template>

<style scoped></style>
