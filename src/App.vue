<template>
  <div id="app">
    <div id="input">
      <h1>FORYARD EMAIL SIGNATURE GENERATOR</h1>
      <p>Fill in these fields, copy the contents of the block below and set it as your email signature.</p>

      <label for="name">Full name</label><br>
      <input type="text" v-model="name" name="name" id="name" placeholder="John Doe">

      <br><br>

      <label for="role">Role</label><br>
      <input type="text" v-model="role" name="role" id="role" placeholder="Developer">

      <br><br>

      <label for="phonenumber">Phone number</label><br>
      +316<input type="number" v-model="phoneNumber" name="phonenumber" id="phonenumber" placeholder="12345678">
    </div>

    <div id="signature">
      <signature-generator :name="name" :role="role" :phone-number="phoneNumber" />
    </div>
  </div>
</template>

<script>
import SignatureGenerator from './components/SignatureGenerator.vue'

export default {
  name: 'app',

  components: {
    SignatureGenerator
  },

  data () {
    return {
      name: '',
      role: '',
      phoneNumber: ''
    }
  }
}
</script>

<style>
#input {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-bottom: 50px;
}

#input label {
  font-size: 18px;
}

#input h1 {
  color: #57EA8A;
}

#signature {
  border: 1px solid #2c3e50;
  border-radius: 10px;
  padding: 50px;
}
</style>