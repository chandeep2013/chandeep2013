///// Html
<html>

<head>
  <link rel="stylesheet" href="css/style.css">
  <script src="JS/methods.js"></script>
  <link href="https://fonts.googleapis.com/css?family=Ubuntu" rel="stylesheet">
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sign in</title>
</head>

<body>
  <div class="main">
    <p class="sign" align="center">Sign in</p>
    <form class="form1">
      <input id="idUserName" class="un " type="text" align="center" placeholder="Username" required="required">
      <input id="idPassWord" class="pass" type="password" align="center" placeholder="Password" required="required">
      <button class="submit" align="center" type="submit" onClick="CheckAuthorization()">Register</button>
      <button class="register" align="center" type="submit" onClick="CheckAuthorization()">Sign in</button>
      <p class="forgot" align="center"><a href="#">Forgot Password?</p>
	  
	  <div class="alert" id="loginMessage" style="display:none;">
		<span class="closebtn" onclick="this.parentElement.style.display='none';">&times;</span> 
		<strong>Login Successful!</strong> 
	  </div>
   
    </div>
     
</body>
</html>

////cssss
body {
    background-color: #F3EBF6;
    font-family: 'Ubuntu', sans-serif;
}

.main {
    background-color: #FFFFFF;
    width: 400px;
    height: 400px;
    margin: 7em auto;
    border-radius: 1.5em;
    box-shadow: 0px 11px 35px 2px rgba(0, 0, 0, 0.14);
}

.sign {
    padding-top: 40px;
    color: #8C55AA;
    font-family: 'Ubuntu', sans-serif;
    font-weight: bold;
    font-size: 23px;
}

.un {
width: 76%;
color: rgb(38, 50, 56);
font-weight: 700;
font-size: 14px;
letter-spacing: 1px;
background: rgba(136, 126, 126, 0.04);
padding: 10px 20px;
border: none;
border-radius: 20px;
outline: none;
box-sizing: border-box;
border: 2px solid rgba(0, 0, 0, 0.02);
margin-bottom: 50px;
margin-left: 46px;
text-align: center;
margin-bottom: 27px;
font-family: 'Ubuntu', sans-serif;
}

form.form1 {
    padding-top: 40px;
}

.pass {
        width: 76%;
color: rgb(38, 50, 56);
font-weight: 700;
font-size: 14px;
letter-spacing: 1px;
background: rgba(136, 126, 126, 0.04);
padding: 10px 20px;
border: none;
border-radius: 20px;
outline: none;
box-sizing: border-box;
border: 2px solid rgba(0, 0, 0, 0.02);
margin-bottom: 50px;
margin-left: 46px;
text-align: center;
margin-bottom: 27px;
font-family: 'Ubuntu', sans-serif;
}


.un:focus, .pass:focus {
    border: 2px solid rgba(0, 0, 0, 0.18) !important;
    
}

.submit {
  cursor: pointer;
    border-radius: 5em;
    color: #fff;
    background: linear-gradient(to right, #9C27B0, #E040FB);
    border: 0;
    padding-left: 40px;
    padding-right: 40px;
    padding-bottom: 10px;
    padding-top: 10px;
    font-family: 'Ubuntu', sans-serif;
    font-size: 13px;
    margin-left: 5%;
    box-shadow: 0 0 20px 1px rgba(0, 0, 0, 0.04);
}
.register {
    cursor: pointer;
      border-radius: 5em;
      color: #fff;
      background: linear-gradient(to right, #9C27B0, #E040FB);
      border: 0;
      padding-left: 40px;
      padding-right: 40px;
      padding-bottom: 10px;
      padding-top: 10px;
      font-family: 'Ubuntu', sans-serif;
      margin-left: 25%;
      font-size: 13px;
      box-shadow: 0 0 20px 1px rgba(0, 0, 0, 0.04);
  }

.forgot {
    text-shadow: 0px 0px 3px rgba(117, 117, 117, 0.12);
    color: #E1BEE7;
    padding-top: 15px;
}

a {
    text-shadow: 0px 0px 3px rgba(117, 117, 117, 0.12);
    color: #E1BEE7;
    text-decoration: none
}

.alert {
  padding: 20px;
  background-color: Green;
  color: white;
}

.closebtn {
  margin-left: 15px;
  color: white;
  font-weight: bold;
  float: right;
  font-size: 22px;
  line-height: 20px;
  cursor: pointer;
  transition: 0.3s;
}

.closebtn:hover {
  color: black;
}

@media (max-width: 600px) {
    .main {
        border-radius: 0px;
    }
    
///////////// Js

function CheckAuthorization() {

    var username = document.getElementById("idUserName").value;
    var Password = document.getElementById("idPassWord").value;

    if (username != "" && Password != "") {
        /////// rest service call
        var get = $.ajax({
            cache: false,
            url: "", // your service name
            type: "GET"
        });
        get.done(function (output) {

            alert("Authentication successfull");
        })
        get.fail(function (err) {
            alert("Authentication Not sucessfull");
        });

    }
    else {
       // alert("Please enter user name and password");
    }
	document.getElementById("loginMessage").style.display = "block";
	setTimeout(function(){
		window.location.href = "home.html";
		}, 3000);
}


