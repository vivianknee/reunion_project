<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <!-- Begin Jekyll SEO tag v2.8.0 -->
<title>SSVG Cars Project | Create Performance Task</title>
<meta name="generator" content="Jekyll v3.9.3" />
<meta property="og:title" content="SSVG Cars Project" />
<meta property="og:locale" content="en_US" />
<meta name="description" content="Create Performance Task" />
<meta property="og:description" content="Create Performance Task" />
<link rel="canonical" href="https://vivianknee.github.io/reunion_project/wishlist.html" />
<meta property="og:url" content="https://vivianknee.github.io/reunion_project/wishlist.html" />
<meta property="og:site_name" content="SSVG Cars Project" />
<meta property="og:type" content="website" />
<meta name="twitter:card" content="summary" />
<meta property="twitter:title" content="SSVG Cars Project" />
<script type="application/ld+json">
{"@context":"https://schema.org","@type":"WebPage","description":"Create Performance Task","headline":"SSVG Cars Project","url":"https://vivianknee.github.io/reunion_project/wishlist.html"}</script>
<!-- End Jekyll SEO tag -->

    <link rel="stylesheet" href="/reunion_project/assets/css/style.css?v=abf67f294fbb08f89d14f52a840be56107174b98">
    <script src="https://code.jquery.com/jquery-1.12.4.min.js" integrity="sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ=" crossorigin="anonymous"></script>
    <script src="/reunion_project/assets/js/respond.js"></script>
   
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
  
  </head>
  <body>
      
    <div class="wrapper">

      <section>
        <!-- nighthawk coding society has altered arrangement and inserted navigation that is updated in independent file -->
        <div id="title">
          <meta name="viewport" content="width=device-width, initial-scale=1">
<style>
  
    @import url('https://fonts.googleapis.com/css2?family=Kanit&display=swap');
    
    .menu {
        overflow: visible;
        background-color: black;
        border: none;
        position: fixed;
        left: 0; 
        right: 0;
        top: 0;
        width: 100%;
        font-family: "Kanit", sans-serif;
        font-size: 20px;
        z-index: 999;
        padding: 0px;
    }

    .menu:hover {
        color:white;
    }
  
    .nav {
        display: block;
        color: rgb(249, 238, 238);
        text-align: center;
        padding: 40px 16px;
        font-family: "Kanit", sans-serif;
        font-size: 20px;
    }

    .nav:hover {
        background-color: rgb(7, 7, 57);
    }

</style>

<body>
<form onsubmit="create_User()" id="signup">
    <h3><label class="title">Sign Up</label></h3>
    
    <p><label class="sign-up-label">
        Username:
        <input type="text" name="username" id="username" required>
    </label></p>
    <p><label class="sign-up-label">
        Password:
        <input type="password" name="password" id="password" required>
    </label></p>
    <p><label class="sign-up-label">
        Verify Password:
        <input type="password" name="passwordV" id="passwordV" required>
    </label></p>
    <p><label class="sign-up-label">
        Email:
        <input type="email" name="email" id="email" required>
    </label></p>
    <br><br>
    <p>
        <button class="createbutton">Create</button>
        <p class="account">Already have an account? <a action="javascript:" onclick="openLog()">Log In</a></p>
    </p>
    <button type="button" class="cancel" onclick="closeSign()">x</button>
</form>
</body>

<script>
    function openSign() {
        document.getElementById("signup").style.display = "block";
    }
    function closeSign() {
        document.getElementById("signup").style.display = "none";
    }
    window.onclick = function (event) {
        let modal = document.getElementById('signupPopup');
        if (event.target == modal) {
    closeSign();
        }
    }
    function create_User(){
        // extract data from inputs
        const username = document.getElementById("username").value;
        const email = document.getElementById("email").value;
        const password = document.getElementById("password").value;
        const requestOptions = {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': 'Bearer my-token',
            },
        };
        //url for Create API
        const url='/api/create/' + username + '/' + email+ '/' + password;
        //Async fetch API call to the database to create a new user
        fetch(url, requestOptions).then(response => {
            // prepare HTML search result container for new output
            const resultContainer = document.getElementById("result");
            // trap error response from Web API
            if (response.status !== 200) {
                const errorMsg = 'Database response error: ' + response.status;
                console.log(errorMsg);
                // Email must be unique, no duplicates allowed
                document.getElementById("pswError").innerHTML =
                    "Email already exists in the table";
                return;
            }
            // response contains valid result
            response.json().then(data => {
                console.log(data);
                //add a table row for the new/created userId
                const tr = document.createElement("tr");
                for (let key in data) {
                    if (key !== 'query') {
                        //create a DOM element for the data(cells) in table rows
                        const td = document.createElement("td");
                        console.log(data[key]);
                        //truncate the displayed password to length 20
                        if (key === 'password'){
                            td.innerHTML = data[key].substring(0,17)+"...";
                        }
                        else{
                            td.innerHTML = data[key];}
                        //add the DOM data element to the row
                        tr.appendChild(td);
                    }
                }
                //append the DOM row to the table
                table.appendChild(tr);
            })
        })
    }
</script>  
    <style>
	@import url('https://fonts.googleapis.com/css2?family=Kanit&display=swap');
    .title {
        font-family: "Kanit", sans-serif;
        font-size: 25px;
        color: white;
        display: grid;
		justify-content: center;
    }

    #login {
        display: none;
        color: white;
        width: 40%;
        height: 50%;
        padding: 50px;
        padding-top: 30px;
        background-color: rgb(16, 15, 15);
        position: fixed;
        left: 50%;
        top: 7%;
        transform: translate(-50%, 25%);
        border: 5px solid white;
        border-radius: 8px;
        z-index: 9;
    }
    .log-in-label {
        color: white;
        font-family: "Kanit", sans-serif;
        font-size: 20px;
        display: grid;
		justify-content: center;
        
    }
    .cancel {
        background-color: white;
        position: fixed;
        top: 15px;
        right: 20px;
        border: none;
        font-weight: bold;
    }

    .cancel:hover {
        color:rgb(4, 4, 43);
    }

    .createbutton {
        background-color: white;
        border-radius: 8px;
        color: black;
        border: none;
        margin: 0;
        position: absolute;
        left: 50%;
     	transform: translate(-50%, -50%);
        font-family: "Kanit", sans-serif;
        font-size: 20px;

    }

    .createbutton:hover {
        color: rgb(4, 4, 43);
    }
    
    .account {
        font-family: "Kanit", sans-serif;
        font-size: 15px;
        color: white;
    }
</style>

<body>
<form onsubmit="create_User()" id="login">
    <h3><label class="title">Login</label></h3>
    
    <p><label class="log-in-label">
        Email:
        <input type="email" name="email" id="email" required>
    </label></p>
    <p><label class="log-in-label">
        Password:
        <input type="password" name="password" id="password" required>
    </label></p>
    <br><br>
    <p>
        <button class="createbutton">Login</button>
        <p class="account">Don't have an account? <a action="javascript:" onclick="openSign()">Sign Up</a></p>
    </p>
    <button type="button" class="cancel" onclick="closeLog()">x</button>
</form>
</body>

<script>
    function openLog() {
        document.getElementById("login").style.display = "block";
    }
    function closeLog() {
        document.getElementById("login").style.display = "none";
    }
    window.onclick = function (event) {
        let modal = document.getElementById('loginPopup');
        if (event.target == modal) {
    closeLog();
        }
    }
    function create_User(){
        // extract data from inputs
        const email = document.getElementById("email").value;
        const password = document.getElementById("password").value;
        const requestOptions = {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': 'Bearer my-token',
            },
        };
        //url for Create API
        const url='/api/create/' + email+ '/' + password;
        //Async fetch API call to the database to create a new user
        fetch(url, requestOptions).then(response => {
            // prepare HTML search result container for new output
            const resultContainer = document.getElementById("result");
            // get error
            if (response.status !== 200) {
                const errorMsg = 'Database response error: ' + response.status;
                console.log(errorMsg);

                document.getElementById("pswError").innerHTML =
                    "Account found, logging you in";
                return;
            }
            // response contains valid result
            response.json().then(data => {
                console.log(data);
                //add a table row for the created user
                const tr = document.createElement("tr");
                for (let key in data) {
                    if (key !== 'query') {
                        //create a DOM element for the data(cells) in table rows
                        const td = document.createElement("td");
                        console.log(data[key]);
                        //truncate the displayed password to length 20
                        if (key === 'password'){
                            td.innerHTML = data[key].substring(0,17)+"...";
                        }
                        else{
                            td.innerHTML = data[key];}
                        //add the DOM data element to the row
                        tr.appendChild(td);
                    }
                }
                //append the DOM row to the table
                table.appendChild(tr);
            })
        })
    }
</script>     
     <table class="menu">
            <tr>
                <td><a href="."><img src="/reunion_project/images/logo.png" width="120px"></a></td> 
                <td><a href="/reunion_project/home" class="nav">Home</a></td>
                <td><a href="/reunion_project/filtertool" class="nav">Car Filter Tool</a></td>
                <td><a href="/reunion_project/specsquiz" class="nav">Specs Quiz</a></td>
                <td><a href="/reunion_project/wishlist" class="nav">Wishlist</a></td>
                <td><a href="/reunion_project/notm" class="nav">Reviews</a></td>
                <td><a action="javascript:" onclick="openSign()" class="nav">Sign-Up/Log-In</a></td>
            </tr>
    </table>
</p>


          <!-- <h1><a href=https://github.com/vivianknee/reunion_project>SSVG Cars Project</a></h1> -->
          <!-- <p>Create Performance Task</p> -->
          <br>
        </div>

        <!-- this is Jekyll magic, each md file in site will be inserted here -->
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />

<html>
    <h1> Car Wish List </h1>
        <p>Choose your ideal car by using the pull-down menu provided below</p>
            <br />
            <button class="selectbutton" id="select_button">Select</button>
            <div>
                <br />
                <div class="select">
                    <form>
                    <label for="brand"> Brand:</label>
                        <select name="brand" id="brand">  
                            <option value="None">None</option>
                            <option value="Honda">Honda</option>
                            <option value="Hyundai">Hyundai</option>
                            <option value="Toyota">Toyota</option>
                            <option value="Chevrolet">Chevrolet</option>
                            <option value="Lexus">Lexus</option>
                            <option value="Tesla">Tesla</option>
                            <option value="Ferrari">Ferrari</option>
                            <option value="Mercedes">Mercedes</option>
                            <option value="Kia">Kia</option>
                            <option value="Mazda">Mazda</option>
                            <option value="Nissan">Nissan</option>
                            <option value="Jeep">Jeep</option>
                            <option value="Acura">Acura</option>
                            <option value="Dodge">Dodge</option>
                            <option value="Ford">Ford</option>
                            <option value="Subaru">Subaru</option>
                            <option value="Audi">Audi</option>
                            <option value="BMW">BMW</option>
                        </select>
                    </form>
                </div>
                <br />
                <div class="select">
                    <form>
                    <label for="color"> Color:</label>
                        <select name="color" id="color">  
                            <option value="None">None</option>
                            <option value="blue">Blue</option>
                            <option value="yellow">Yellow</option>
                            <option value="black">Black</option>
                            <option value="gray">Gray</option>
                            <option value="white">White</option>
                            <option value="red">Red</option>
                            <option value="silver">Silver</option>
                        </select>
                    </form>
                </div>
                <br />
                <div class="select">
                    <form>
                    <label for="type"> Type:</label>
                        <select name="type" id="type">  
                            <option value="None">None</option>
                            <option value="suv">SUV</option>
                            <option value="truck">Truck</option>
                            <option value="sedan">Sedan</option>
                            <option value="sports">Sports</option>
                        </select>
                    </form>
                 </div>
                 <br />
                 <div class="select">
                    <form>
                    <label for="powersource"> Powersource:</label>
                        <select name="powersource" id="powersource">
                            <option value="None">None</option>  
                            <option value="ice">ICE</option>
                            <option value="hybrid">Hybrid</option>
                            <option value="electric">Electric</option>
                        </select>
                    </form>
                 </div>
                 <br />
                 <div class="select">
                    <form>
                    <label for="pricerange"> Price Range:</label>
                        <select name="pricerange" id="pricerange">  
                            <option value="None">None</option>
                            <option value="10-15k">10-15k</option>
                            <option value="15-35k">15-35k</option>
                            <option value="35-70k">35-70k</option>
                            <option value="70k+">70k+</option>
                        </select>
                    </form>
                </div>
                <br />
                <table class="table-latitude">
                <thead>
                    <tr>
                        <th></th>
                        <th>Brand</th>
                        <th>Color</th> 
                        <th>Type</th>
                        <th>Power Source</th>
                        <th>Price Range</th>
                    </tr>
                    </thead>
                     <tbody id="result">
                    </tbody>
                </table>
            </div>
  </html>

<style>
    select {
        -webkit-appearance:none;
        -moz-appearance:none;
        -ms-appearance:none;
        appearance:none;
        outline:0;
        box-shadow:none;
        border:0!important;
        background: #5c6664;
        background-image: none;
    }

    select:: -ms-expand {
        display: none;
    }

    .select {
        position: relative;
        display: flex;
        width: 15em;
        height: 2em;
        line-height: 2;
        background: #5c6664;
        overflow: hidden;
        border-radius: .25em;
    }

    select {
        flex: 1;
        padding: 0 .5em;
        color: #fff;
        cursor: pointer;
        font-size: 1em;
        font-family: "Kanit", sans-serif;
    }

    .select::after {
        content: '\25BC';
        position: absolute;
        top:0;
        right: 0;
        padding: 0 1em;
        background: #fff;
        cursor: pointer;
        pointer-events:none;
        transition: .25s all ease;
        color: black;
    }

    .select:hover::after {
        color: navy;
    }

    .selectbutton {
        background-color: white;
        border-radius: 8px;
        color: black;
        border: none;
        margin: 0;
        font-family: "Kanit", sans-serif;
        font-size: 16px;
    }

    .selectbutton:hover {
        color: rgb(4, 4, 43);
    }

    h1 {
        font-family: "Kanit", sans-serif;
        font-size: 30px;
        color: white;
    }

    p {
        font-family: "Kanit", sans-serif;
        font-size: 15px;
        color: white;
    }

    #prices {
    font-family: "Kanit", sans-serif;
    border-collapse: collapse;
    table-layout: fixed;
    }

    #prices td, #prices th {
    border: 1px solid #ddd;
    padding: 8px;
    }

    #prices th {
    padding-top: 12px;
    padding-bottom: 12px;
    text-align: left;
    background-color: beige;
    color: black;
    }

</style>

<script>
    const btnSelect = document.getElementById("select_button");
    const resultContainer = document.getElementById("result");
    const brand_wish = document.getElementById("brand");
    const color_wish = document.getElementById("color");
    const type_wish = document.getElementById("type");
    const powersource_wish = document.getElementById("powersource");
    const pricerange_wish = document.getElementById("pricerange");

    btnSelect.addEventListener('click', (event) => {
          console.log("Select Clicked!");
          clearTable();
          
          if( brand_wish.value == "None" && color_wish.value == "None" && type_wish.value== "None" && powersource_wish.value == "None" && pricerange_wish.value == "None"){
            alert('Select at least one option')
            return
          }

          var car_brand_value = brand_wish.value;
          var car_color_value = color_wish.value; 
          var car_type_value = type_wish.value; 
          var car_powersource_value = powersource_wish.value;
          var car_pricerange_value = pricerange_wish.value; 

          var car_wish_list = addToWishList(car_brand_value, car_color_value, car_type_value, car_powersource_value, car_pricerange_value);
            return
          }

          console.log(car_wish_list);
          console.log("Creating table!");

          for (const car of car_wish_list) {
            console.log(car);

            const tr = document.createElement("tr");
  
            const brand_ele = document.createElement("td");
            brand_ele.innerHTML = car.brand;

            const color_ele = document.createElement("td");
            color_ele.innerHTML = car.color;

            const type_ele = document.createElement("td");
            type_ele.innerHTML = car.type;

            const powersource_ele = document.createElement("td");
            powersource_ele.innerHTML = car.powersource;

            const price_ele = document.createElement("td");
            //put if statement here later
            price_ele.innerHTML = car.pricerange;

            // this builds ALL td's (cells) into tr element
            tr.appendChild(brand_ele);
            tr.appendChild(color_ele);
            tr.appendChild(type_ele);
            tr.appendChild(powersource_ele);
            tr.appendChild(price_ele);

            resultContainer.appendChild(tr);
          }
    });

    function clearTable() {
        var tableRows = resultContainer.getElementsByTagName('tr');
        var rowCount = tableRows.length;

        for (var x=rowCount-1; x>=0; x--) {
            resultContainer.removeChild(tableRows[x]);
        }
    }
    

    function addToWishList(brand, color, type, powersource, pricerange) {
        var result = [];
        var car; 

        car["brand"] = brand;
        car["color"] = color;
        car["type"] = type;
        car["powersource"] = powersource;
        car["pricerange"] = pricerange;

        result.push(car);

        console.log(car);
        return result;
    }

  </script>

      </section>

    </div>
  </body>
</html>
