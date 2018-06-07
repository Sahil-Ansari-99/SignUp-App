# SignUp-App
Shaastra SignUp App
Here is the code:

<html ng-app>
<head>
<meta name="viewport" content="width=device-width,initial scale=1">
<style>
form
{
	padding:10px;
	font-family:arial;
}
.wrap
{
	width:400px;
	background:white;
	padding:10px;
	border-radius:10px;
	margin:auto;
	opacity:.8;
}
input
{
	padding:10px;
	margin:10px;
	border-radius:5px;
	border:1px solid light pink;
	text-color:black;
	width:90%;
}
option,select
{
	padding:10px;
	margin:5px;
	border-radius:5px;
	border:1px solid light pink;
	color:black;
}
input[type=submit]
{
	width:80%;
	background:#fc4a24;
	color:white;
	cursor:hand;
	font-size:18px;
	font-weight:bold;
	border-radius:10px;
}
span
{
	font-weight:bold;
	font-family:Arial;
	color:black;
}
h1
{
	font-family:Courier new;
}
.img
{
	margin:auto;
	width:350px;
	height:250px;
}

input.ng-invalid.ng-dirty
{
	border-color: red;
}

.error
{
	color: red;
	font-weight:bold;
	font-family:Courier new;
}

	
</style>
<script type="text/javascript">
function check()
{
	var cpass=document.getElementById('cpass').value;
	var pwd=document.getElementById('pwd').value;
	if(cpass!=pwd)
	{
		document.getElementById('pass_error').innerHTML="Passwords donot match";
		document.getElementById('cpass').style.borderColor="red";
		return false;
	}
}
</script>

</head>
<body background="back6.jpg" height="100%">
<div class="img">
<a href="#">
<img src="Shaastralogo.png" alt="Shaastra" height="250px" width="350px" title="Back to home page"></img></a>
</div>
<div class="wrap">
<h1 align="center"> Sign Up</h1>

<form name="SignIn" onsubmit="return check()" action="#">
<span>First Name:</span><br>
<input type="text" name="firstname" placeholder="Enter your first name"  ng-model="fname" required><br>
<span ng-show="SignIn.firstname.$dirty && SignIn.firstname.$error.required" class="error">Please enter first name</span><br>
<span>Last Name:</span><br>
<input type="text" name="lastname" placeholder="Enter your last name" ng-model="lname" required><br>
<span  ng-show="SignIn.lastname.$dirty && SignIn.lastname.$error.required" class="error">Please enter last name</span><br>
<span>Shaastra ID:</span><br>
<input type="tel" name="shaastraid" placeholder="Shaastra ID" ng-model="shasid" required><br>
<span  ng-show="SignIn.shaastraid.$dirty && SignIn.shaastraid.$error.required" class="error">Please enter Shaastra ID</span><br>
<span>Phone Number:</span><br>
<input type="tel" name="num" placeholder="Enter your Phone Number" ng-model="num" ng-minlength="10" ng-maxlength="10" required><br>
<span ng-show="SignIn.num.$dirty && SignIn.num.$error.required" class="error">Please enter mobile number</span>
<span ng-show="SignIn.num.$dirty && SignIn.num.$error.minlength" class="error">Number should have 10 digits</span>
<span ng-show="SignIn.num.$dirty && SignIn.num.$error.maxlength" class="error">Number should have 10 digits</span>
<span ng-show="SignIn.num.$dirty && SignIn.num.$error.number" class="error">Invalid number</span><br>
<span>Email:</span><br>
<input type="email" name="email" placeholder="Enter your email" ng-model="email" required><br>
<span ng-show="SignIn.email.$dirty && SignIn.email.$error.required" class="error">Please enter email</span>
<span ng-show="SignIn.email.$dirty && SignIn.email.$error.email" class="error">Invalid email</span><br>
<span>State:</span><br>
<input list="States" name="State" id="stt" placeholder="Select your State">
<datalist id="States">
<option value="Andhra Pradesh">Andhra Pradesh</option>
<option value="Arunachal Pradesh">Arunchal Pradesh</option>
<option value="Assam">Assam</option>
<option value="Andaman and Nicobar Islands">Andaman and Nicobar Islands</option>
<option value="Bihar">Bihar</option>
<option value="Chandigarh">Chandigarh</option>
<option value="Chhattisgarh">Chhattisgarh</option>
<option value="Dadra and Nagar Haveli">Dadra and Nagar Haveli</option>
<option value="Daman and Diu">Daman and Diu</option>
<option value="Delhi">Delhi</option>
<option value="Goa">Goa</option>
<option value="Gujarat">Gujarat</option>
<option value="Haryana">Haryana</option>
<option value="Himachal Pradesh">Himachal Pradesh</option>
<option value="Jammu & Kashmir">Jammu & Kashmir</option>
<option value="Jharkhand">Jharkhand</option>
<option value="Karnataka">Karnataka</option>
<option value="Kerela">Kerela</option>
<option value="Lakshadweep">Lakshadweep</option>
<option value="Madhya Pradesh">Madhya Pradesh</option>
<option value="Maharashtra">Maharashtra</option>
<option value="Manipur">Manipur</option>
<option value="Meghalaya">Meghalaya</option>
<option value="Mizoram">Mizoram</option>
<option value="Nagaland">Nagaland</option>
<option value="Odisha">Odisha</option>
<option value="Puducherry">Puducherry</option>
<option value="Punjab">Punjab</option>
<option value="Rajasthan">Rajasthan</option>
<option value="Sikkim">Sikkim</option>
<option value="Tamil Nadu">Tamil Nadu</option>
<option value="Telangana">Telangana</option>
<option value="Tripura">Tripura</option>
<option value="Uttarakhand">Uttarakhand</option>
<option value="Uttar Pradesh">Uttar Pradesh</option>
<option value="West Bengal">West Bengal</option>
</datalist><br>
<span id="state_error" class="error"></span><br>
<span>Password:</span><br>
<input type="password" name="password" id='pwd' placeholder="Enter Password" ng-model="password" ng-minlength="6" required><br>
<span ng-show="SignIn.password.$dirty && SignIn.password.$error.required" class="error">Please enter password</span>
<span ng-show="SignIn.password.$dirty && SignIn.password.$error.minlength" class="error">Password should have atleast 6 characters</span><br>
<span>Confirm Password:</span><br>
<input type="password" name="cpass" id="cpass" placeholder="Confirm Password" ng-model="conpass" ng-minlength="6" required><br>
<span ng-show="(conpass!=password) && SignIn.cpass.$dirty" class="error" id="pass_error">Passwords donot match</span><br>
<input type="submit" value="Register" ng-disabled="SignIn.$invalid"></input>


</form>
</div>
<script src="http://code.angularjs.org/1.2.3/angular.min.js">
</script>

</body>
</html>
