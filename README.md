# Responsive Sliding Login & Registration

style: 

* {
margin: 0;
padding: 0;
box-sizing: border-box;
font-family: 'poppins', sans-serif;
}
body {
   display: flex;
   justify-content: center;
   align-items: center; 
   min-height: 100vh;
   background-color: #03a9f4;
}

body.active{
 background-color: #f43648;;
}

.container{
 position: relative;
 width: 800px;
 height: 500px;
 margin: 20px;
}

.BlueBg{
position: absolute;
top: 40px;
width: 100%;
height: 420px;
display: flex;
justify-content: center;
align-items: center;
background: rgb(250, 250, 250,0.2);
box-shadow: 0 5px 45px rgb(0, 0, 0,0.15);
}  

.BlueBg .box {
position: relative;
width: 50%;
height: 100%;
display: flex;
justify-content: center;
align-items: center;
flex-direction: column;
}

.BlueBg .box h2 {
    color: #fff;
    font-size: 1.2em;
    font-weight: 500;
    margin-bottom: 10px;
}

.BlueBg .box button 
{
 cursor:pointer;
 padding: 10px 20px;
 background: #fff;
 color: #333;
 font-size: 16px;
 font-weight: 500;
 border: none;
}
.formBx {
   position: absolute;
   top: 0;
   left: 0;
   width: 50%;
   height: 100%;
   background: #fff;
   z-index: 1000;
   display: flex;
   justify-content: center;
   align-items: center;
   box-shadow: 0 5px 45px rgb(0, 0, 0, 0,0.25);
   transition: 0.5s ease-in-out;
   overflow: hidden;
}

.formBx.active {
  left: 50%;
} 

.formBx .form 
{
 position: absolute;
 left: 0;
 width: 100%;
 padding: 50px;
 transition: 0.5s;
}

.formBx .signinForm {
  transition-delay: 0.25s;
}

.formBx.active .signinForm
{
 left: -100%;
 transition-delay: 0s;
}

.formBx .signUpForm {
    left: 100%;
    transition-delay: 0s;
}

.formBx.active .signUpForm {
    left: 0%;
    transition-delay: 0.25s;
}

.formBx .form form{
    width: 100%;
    display: flex;
    flex-direction: column;
}

.formBx .form form h3{
 font-size: 1.5em;
 color: #333;
 margin-bottom: 20px;
 font-weight: 500 ;
}

.formBx .form form input{
    width: 100%;
    margin-bottom: 20px;
    padding: 10px;
    outline: none;
    font-size: 16px;
    border: 1px solid #333;
}

.formBx .form form input[type="submit"]
{
    background: #03a9f4;
    border: none;
    color: #fff;
    max-width: 100px;
    cursor: pointer;
}

.formBx.active .signUpForm input[type="submit"]
{
    background: #f43648;
}

.formBx .form form .forgot{
    color: #333;
}


@media (max-width: 991px)
{
    .container
    {
        max-width: 400;
        height: 650px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .container .BlueBg
    {
        top: 0;
        height: 100%;

    }
    .formBx
    {
        width: 100%;
        height: 500px;
        top: 0;
        box-shadow: none;
    }
    .BlueBg .box
    {
        position: absolute;
        width: 100%;
        height: 150px;
        bottom: 0;
    }
    .box.signin
    {
        top: 0;
    }
    .formBx.active
    {
        left: 0;
        top: 150px
    }
}
html 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sliding</title>
    <link rel="stylesheet" href="style.css">
</head>
<body> 
    <div class="container">
      <div class="BlueBg">
        <div class="box signin">
            <h2>Already Have an Account</h2>
            <button class="signinBtn">Sign in</button>
        </div>
        <div class="box signup">
            <h2>don´t Have an Account</h2>
            <button class="signupBtn">Sign up</button>
        </div>
      </div> 
      <div class=formBx>
          <div class="form signinForm">
              <form>
                  <h3>Sign In</h3>
                  <input type="text" placeholder="Username">
                  <input type="password" placeholder="Password">
                  <input type="submit" value="Login">
                  <a href="#"class="forgot">Forgot Password</a>
              </form>
          </div>

          <div class="form signUpForm">
            <form>
                <h3>Sign Up</h3>
                <input type="text" placeholder="Username">
                <input type="text" placeholder="Email Address">
                <input type="password" placeholder="Password">
                <input type="password" placeholder="Confirm Password">
                <input type="submit" value="Register">
            </form>
        </div>
      </div>
    </div> 


    <script>
        const signinBtn = document.querySelector('.signinBtn');
        const signupBtn = document.querySelector('.signupBtn');
        const formBx = document.querySelector('.formBx');
        const body = document.querySelector('body')

        signupBtn.onclick =function(){
           formBx.classList.add('active')
           body.classList.add('active')
        }

        signinBtn.onclick =function(){
           formBx.classList.remove('active')
           body.classList.remove('active')
        }
    </script>



  </body>
</html>


