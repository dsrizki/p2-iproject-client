<script>
import { useAllStateStore } from "../stores/allState";
import { mapActions } from "pinia";

export default {
  data() {
    return {
      objFormUser: {
        phoneNumber: '',
      },
    }
  },
  methods: {
    ...mapActions(useAllStateStore, ['registerHandler']),
    onSubmitLogoutHandler() {
      this.registerHandler(this.objFormUser);
    }
  }
}
</script>

<template>
  <!-- Modal HTML -->
  <div id="myModalRegister"
       class="modal fade">
    <div class="modal-dialog modal-login">
      <div class="modal-content">
        <div class="modal-header">
          <div class="avatar">
            <img src="../assets/avatar.jpg"
                 alt="Avatar">
          </div>
          <h4 class="modal-title">Member Register</h4>
          <button type="button"
                  class="close"
                  data-dismiss="modal"
                  aria-hidden="true">&times;</button>
        </div>
        <div class="modal-body">
          <form @submit.prevent="onSubmitLogoutHandler">
            <div class="form-group">
              <input v-model="objFormUser.phoneNumber"
                     type="text"
                     class="form-control"
                     name="username"
                     placeholder="Username"
                     required="required">
            </div>
            <div class="form-group">
              <!-- <input type="password"
                     class="form-control"
                     name="password"
                     placeholder="Password"
                     required="required"> -->
            </div>
            <div class="form-group">
              <button type="submit"
                      class="btn btn-primary btn-lg btn-block login-btn">Register</button>
            </div>
          </form>
        </div>
        <div class="modal-footer">
          <a href="#">Forgot Password?</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
body {
  font-family: 'Varela Round', sans-serif;
}

.modal-login {
  color: #636363;
  width: 350px;
}

.modal-login .modal-content {
  padding: 20px;
  border-radius: 5px;
  border: none;
}

.modal-login .modal-header {
  border-bottom: none;
  position: relative;
  justify-content: center;
}

.modal-login h4 {
  text-align: center;
  font-size: 26px;
  margin: 30px 0 -15px;
}

.modal-login .form-control:focus {
  border-color: #70c5c0;
}

.modal-login .form-control,
.modal-login .btn {
  min-height: 40px;
  border-radius: 3px;
}

.modal-login .close {
  position: absolute;
  top: -5px;
  right: -5px;
}

.modal-login .modal-footer {
  background: #ecf0f1;
  border-color: #dee4e7;
  text-align: center;
  justify-content: center;
  margin: 0 -20px -20px;
  border-radius: 5px;
  font-size: 13px;
}

.modal-login .modal-footer a {
  color: #999;
}

.modal-login .avatar {
  position: absolute;
  margin: 0 auto;
  left: 0;
  right: 0;
  top: -70px;
  width: 95px;
  height: 95px;
  border-radius: 50%;
  z-index: 9;
  background: #60c7c1;
  padding: 15px;
  box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
}

.modal-login .avatar img {
  width: 100%;
}

.modal-login.modal-dialog {
  margin-top: 80px;
}

.modal-login .btn,
.modal-login .btn:active {
  color: #fff;
  border-radius: 4px;
  background: #60c7c1 !important;
  text-decoration: none;
  transition: all 0.4s;
  line-height: normal;
  border: none;
}

.modal-login .btn:hover,
.modal-login .btn:focus {
  background: #45aba6 !important;
  outline: none;
}

.trigger-btn {
  display: inline-block;
  margin: 100px auto;
}
</style>