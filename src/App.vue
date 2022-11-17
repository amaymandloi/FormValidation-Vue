<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/SignUp">SignUp</router-link>
    </nav>
    <router-view/>
    <div class="header">
            <div class="title"><img src="https://www.tcsion.com/dotcom/TCSSMB/Login/images/TATA-logo-left.png"
                    alt="Tata Logo" /></div>
            <div class="title_img"><img src="https://www.tcsion.com/dotcom/TCSSMB/Login/images/TATA-logo-right.png"
                    alt="Tata Logo" /></div>
    </div>
        <div class="menu-items">
            <img src="@/assets/tcsionimg.png">
            <div class="items">
                <a id="phoneno"> 1800 029 6030</a> |
                <a id="redtext"> SMS: 'TCSiON' to 16161</a> |
               <a id="phoneno"> Email US </a> |
                <a id="phoneno"> Visit Our Portal </a> |
               <a id="phoneno"> Help Central </a> |
                <a id="phoneno"> Language : </a>

                <select name="English">
                    <option value="English">English</option>
                    <option value="Spanish">Spanish</option>
                    <option value="Japanese">Japanese</option>
                    <option value="Bahasa">Bahasa</option>
                    <option value="Portugese">Portugese</option>
                </select>

            </div>
        </div>

        <div class="content">

<div class="left-content">
    <img src="@/assets/ion-login-banner.jpg">
    <div id="text-wrapper">
        Experience the <a id="best"> Best </a><br>
        with all new <a id="orange">TCS iON</a>
    </div>
</div>
<div class="right-content">
    <form @submit="signup">
        <div class="form-control">
        <h1>Welcome</h1>
        <p id="error" v-if="error.length">
        <ul>
        <li v-for="e in error" v-bind:key="e.id">
       {{e}}
       </li>
       </ul>
       </p>
        <label for="username">Username:</label>
        <input type="text" 
        placeholder="Username" 
        id="username" name="username" 
        v-model = "username"/>
        </div>

        <div class = "form-control">
        <label for="email">Email:</label>
        <input type="email" 
        placeholder="Email"
         id="email" v-model="email"/>
        
      
        </div>

        <div class="form-control">
         <label for="Gender">Gender</label><br> 
        <input id="radiobtn" type="radio" v-model="gender" value="male"/>Male
        <input id="radiobtn" type="radio" v-model="gender" value="female" >Female<br>
        </div>

        <div class="form-control">
        <label for="Password">Password:</label>
        <input type="password" 
        name="password"
        placeholder="Password"
         id="psw" v-model="password"/>
         
         </div>

         <div class="form-control">
            <label for="ConfirmPassword">Confirm Password:</label>
            <input type="password" 
            name="ConfirmPassword"
            placeholder="ConfirmPassword"
             id="conPsw" v-model="ConfirmPassword"/>
             </div>

        <div>
        <button type="submit" id="submit"> Submit</button>
        </div>
    
    </form>
        </div>
        </div>
        </div>
</template>
<script>
export default {
  data()
  {
    return{
      error : [],
      username : null,
      email : null,
      gender : null,
      password : null,
      ConfirmPassword : null
    }
  },
  methods:
  { 
    
    signup : function (e)
      {
         this.error=[];
         if(this.username && this.email && this.password && this.ConfirmPassword){
          console.warn("no error")
          // store username in object and show in console.
         }
         if(!this.username){
          this.error.push("Username is required");
         }
         if(!this.email){
          this.error.push("email is required")
         }
         if(!this.gender){
          this.error.push("gender is required")
         }
          if(!this.password){
           this.error.push("password is required")
          }
          if(!this.ConfirmPassword){
           this.error.push("Confirm is required")
         }
         if(this.password !== this.ConfirmPassword){
          this.error.push("Password and Confirm Password is not same")
         }

         
        console.warn("success",this.error);
        e.preventDefault();
      },
      validEmail: function (email) {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    }
  }
}
</script>
<style>
#error{
 color: red;
}
.header {
  height: 28px;
  background-color: #2d3540;
  color: #fff;
  width: 100%;
}

.title {
  padding: 4px 3%;
  float: left;
}

.title_img {
  padding: 5px 3%;
  float: right;
}

div {
  display: block;
}

.n-footer {
  background: #043254 none repeat scroll 0 0;
  /* top:90%; */
  bottom: 0;
  position: fixed;
  width: 100%;
  text-align: center;
  padding: 10px 0;
}

#year1 {
  font-size: 1em;
  vertical-align: 0px;
}

.footer-content {
  display: inline-block;
  float: right;
  margin-right: 3%;
  margin-left: 2px;
}

.circle {
  background: #00aade none repeat scroll 0 0;
  border-radius: 50%;
  color: #ffffff;
  display: inline-block;
  font-size: 0.9em;
  width: 23px;
  height: 21px;
  padding-top: 2px;
}

.footer {
  color: #fff;
  font-size: 0.8em;
  font-weight: 600;
  float: left;
  margin-left: 3%;
  line-height: 23px;
}

.menu-items img {
  height: 100px;
  width: 250px;
}

.items {
  font-size: small;
  float: right;
  /* background-color: #00aade; */
  margin-right: 0%;
  margin-top: 25px;
  border-bottom: #00aade;
  border-width: 12px;
}

.right-content {
  color: white;
  background-color: rgb(125, 125, 254);
  display: inline;
  float: right;
  margin-right: 20%;
  margin-left: 60px;
  margin-bottom: 60px;
  padding: 10px 10px 10px 10px;
  border-radius: 10px;
  height: 550px;
  width: 450px;
}

.left-content {
  display: inline;
  float: left;
}


.left-content img {
  margin-left: 90px;
}

.right-content form a {
  font-size: small;
  float: right;
  margin-right: 30px;
  color: white;
}

.right-content form input {
  width: 90%;
  height: 20%;
  padding: 10px 10px 10px 10px;
  margin: 10px 10px 10px 10px;
}

.right-content form h1 {
  font-size: xx-large;
  font-weight: 600;
}

.right-content form .checkbx {
  float: left;
  font-size: small;
}

.right-content form {
  padding-left: 25px;
  padding-right: 25px;
}

.right-content form .btn1 {
  position: absolute;
  background-color: rgb(27, 192, 33);
  color: white;
  font-size: 16px;
  padding: 10px 20px;
  border: none;
  box-shadow: #2d3540;
  cursor: pointer;
  border-radius: 0px;
  align-items: center;
}

.right-content form .btn:hover {
  background-color: black;
}

.right-content form .checkbx {
  width: 10px;
}

.right-content .banner {
  background-color: white;
  width: 100%;
  height: 60px;
}

.n-footer .division {
  background-color: white;
  padding-top: 0 0 0 0;
  text-align: center;
  margin-top: 0%;
  color: orange;
  height: 60px;
  width: 100%;
  margin-top: 0px;
}

#radiobtn {
  width: 10px;
  height: 10px;
}

select {
  border-color: blue;
}

#phoneno {
  color: blue;
  font-weight: 800;
}

#redtext {
  color: red;
  font-weight: 800;
}

#best {
  color: blue;
  font-weight: 700;
}

#orange {
  color: orange;
  font-weight: 700;
}

#text-wrapper {
  margin-left: 120px;
  font-size: larger;
  font-weight: 600;
  width: 300px;
  height: 50px;
}
small{
  color: red;
  font-weight: 500;
}

</style>
