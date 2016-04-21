<template>
  <div class="col-sm-6 col-sm-offset-3">
    <center><h2><b>PIC Account Registration</b></h2>
      <p>Sign up for a free account to get some great quotes.</p></center>
      <div class="alert alert-danger" v-if="error">
        <p>{{ error }}</p>
      </div>
    </div>
    <div class="col-sm-offset-2 col-sm-8">
      <div class="form-horizontal">
        <div class="form-group">
          <label for="inputEmail3" class="col-sm-3 control-label">SKK Grup</label>
          <div class="col-sm-7">
            <select
            class="form-control"
            v-model="credentials.kksgroup"
            >
            <option
            value="" disabled selected
            >Select your SKK Group
            </option>
            <option
            value="KKS Group 1"
            >KKS Group 1
          </option>
          <option
          value="KKS Group 2"
          >KKS Group 2
        </option>
      </select>
    </div>
  </div>
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-3 control-label">PIC Name</label>
    <div class="col-sm-7">
      <input 
      type="text" 
      class="form-control"
      placeholder="Enter your PIC Name"
      v-model="credentials.picname"
      >
    </div>
  </div>
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-3 control-label">PIC Email</label>
    <div class="col-sm-7">
      <input 
      type="email" 
      class="form-control"
      placeholder="Enter your PIC Email"
      v-model="credentials.email"
      >
    </div>
  </div>
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-3 control-label">PIC Phone</label>
    <div class="col-sm-7">
      <input 
      type="text" 
      class="form-control"
      placeholder="Enter your PIC Phone"
      v-model="credentials.phone"
      >
    </div>
  </div>
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-3 control-label">Scanned Letter</label>
    <div class="col-sm-7">
      <input 
      type="file" 
      class="form-control"
      placeholder="Enter your PIC Phone"
      v-model="credentials.scannedlatter"
      >
    </div>
  </div>
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-3 control-label">Username</label>
    <div class="col-sm-7">
      <input 
      type="text" 
      class="form-control"
      placeholder="Enter your username"
      v-model="credentials.username"
      >
    </div>
  </div>
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-3 control-label">Password</label>
    <div class="col-sm-7">
      <input 
      type="password" 
      class="form-control"
      placeholder="Enter your password"
      v-model="credentials.password"
      >
    </div>
  </div>
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-3 control-label">Re-Password</label>
    <div class="col-sm-7">
      <input 
      type="password" 
      class="form-control"
      placeholder="Enter your password again"
      v-model="credentials.repassword"
      >
    </div>
  </div>
  <div class="col-sm-offset-3 col-sm-7">
  <button class="btn btn-primary btn-lg btn-block btn-sm" @keyup.enter="submit()">Submit Registration</button>
  </div>
</div>
</div>
</template>

<script>
  import auth from '../auth'

  export default {

    data() {
      return {
        credentials: {
          kksgroup: '',
          picname: '',
          email: '',
          phone: '',
          scannedlatter: '',
          username: '',
          password: '',
          repassword: '',
        },
        error: ''
      }
    },

    methods: {

      submit() {

        var credentials = {
          kksgroup: this.credentials.kksgroup,
          picname: this.credentials.picname,
          email: this.credentials.email,
          phone: this.credentials.phone,
          scannedlatter: this.credentials.scannedlatter,
          username: this.credentials.username,
          password: this.credentials.password,
          repassword: this.credentials.repassword,
          
        }

        auth.signup(this, credentials, 'login')
      }
    }
  }
</script>