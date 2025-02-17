<script setup lang="ts">
import { ref } from 'vue'

let loading = ref(false)

const form = ref<any>({
  email: '',
  password: '',
})

function signIn(val: any) {
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
            name="sign-in-form"
            layout="vertical"
            :model="form"
            @finish="signIn"
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

            <a-form-item>
              <a-button type="primary" html-type="submit" :loading="loading">Login</a-button>
            </a-form-item>

            <a-form-item>
              <p>
                Don't have an account?
                <RouterLink to="/sign-up"> Create account </RouterLink>
              </p>
            </a-form-item>
          </a-form>
        </a-card>
      </a-col>
    </a-row>
  </div>
</template>

<style scoped></style>
