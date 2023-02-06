<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    h1 {
        font-family: "Kanit", sans-serif;
        font-size: 30px;
        color: white;
    }
    h2 {
        color: red;
        font-size: 25px;
        font-family: Impact;

    }
</style>

<html>

<h1>Sign-Up</h1>

<h2> <b>Note: Our password collection system is not fully protected, please do not input any passwords that could compromise other services you utilize. We will also avoid accepting emails as these two can be linked to hack other services if the warning above is ignored. </b></h2>


<form action="create_User()">
    <p><label>
        Name:
        <input type="text" name="name" id="name" required>
    </label></p>
    <p><label>
        User ID:
        <input type="text" name="uid" id="uid" required>
    </label></p>
    <p><label>
        Password:
        <input type="password" name="password" id="password" required>
        Verify Password:
        <input type="password" name="passwordV" id="passwordV" required>
    </label></p>
    <p><label>
        Phone:
        <input type="tel" name="phone_num" id="phone_num"
            pattern="[0-9]{3}-[0-9]{3}-[0-9]{4} | [0-9]{10}"
            placeholder="999-999-9999">
    </label></p>
    <p><label>
        Birthday:
        <input type="date" name="dob" id="dob">
    </label></p>
    <p>
        <button type="submit" class="signupbtn"> Create</button>
    </p>
</form>

</html>

<script>

    function create_User(){
    // extract data from inputs
    const name = document.getElementById("name").value;
    const email = document.getElementById("email").value;
    const password = document.getElementById("password").value;
    const phone = document.getElementById("phone").value;
    const requestOptions = {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
            'Authorization': 'Bearer my-token',
        },
    };
    //url for Create API
    const url='/crud_api/create/' + name + '/' + email+ '/' + password + '/' + phone;
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