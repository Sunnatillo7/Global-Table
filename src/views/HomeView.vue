<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <!-- <appTable :headers="headers" :body="users">

        </appTable> -->
        <Form @submit="login">
          <Field
          rules="required"
          :modelValue="form.first_name"
          v-slot="{ errors }"
          name="email"
          >
          <input type="text" v-model="form.first_name">
          <p class="login__input-error" v-if="errors && errors.length">
               {{ errors[0] }}
          </p>
          </Field>
          <button type="submit">submit</button>
        </Form>
      </div>
    </div>
  </div>
</template>

<script setup>
import {Form,Field} from 'vee-validate'
import { onMounted, ref } from 'vue';
import appModal from '@/components/ui/app-modal.vue';
import appTable from '@/components/ui/app-table.vue';
import Notification from '@/plugins/Notification'
import axios from 'axios'
// const count = computed(() => store.getters.getCounter)
// const auth = computed(() => store.getters.getAuth)
const dialog = ref(false)
// const headers = ref([
//   {title: 'T/R', value:'id'},
//   {title: 'Name', value:'name'},
//   {title: 'Username', value:'username'},
//   {title: 'Email', value:'email'},
// ])
const users = ref([])
const form = ref({
  first_name: '',
  number: null
})
const login =()=>{
  console.log('login')
}
// const getUsers =()=>{
//   axios.get('https://jsonplaceholder.typicode.com/users').then(res=>{
//     console.log(res.data)
//     users.value = res.data
//   })
// }
// const Success =()=>{
//   Notification({ text: "Product delete !!!" },{type: 'danger'})
// }
// getUsers()
</script>

<style scoped>
.login_input-error{
  margin-top: 5px;
        color: red;
        font-size: 15px;
        font-weight: 500;
}
</style>
