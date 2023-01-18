
<style>
     <style>
     a {
    color: white;
    }
</style>
    
</style>

<html>
    
<header>
    <body>
        <table>
        <thead>
        <tr>
            <th>Name</th>
            <th>ID</th>
            <th>Actions</th>
        </tr>
        </thead>
            <tbody id="table">
            <!-- javascript generated data -->
            </tbody>
        </table>
    </body>

</header>

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

    const json = '[{"_name": "Thomas Edison", "_uid": "toby"}, {"_name": "Nicholas Tesla", "_uid": "nick"}, {"_name": "John Mortensen", "_uid": "jm1021"}, {"_name": "Eli Whitney", "_uid": "eli"}, {"_name": "Hedy Lemarr", "_uid": "hedy"}]';

        const data = JSON.parse(json);

        const table = document.getElementById("table"); 
        data.forEach(user => {
             // build a row for each user
            const tr = document.createElement("tr");

            // td's to build out each column of data
            const name = document.createElement("td");
            const id = document.createElement("td");
            const action = document.createElement("td");
                
            // add content from user data          
            name.innerHTML = user._name; 
            id.innerHTML = user._uid; 

            // add action for update button
            var updateBtn = document.createElement('input');
            updateBtn.type = "button";
            updateBtn.className = "button";
            updateBtn.value = "Update";
            updateBtn.style = "margin-right:16px";
            updateBtn.onclick = function () {
            alert("Update: " + user._uid);
            };
            action.appendChild(updateBtn);

            // add action for delete button
            var deleteBtn = document.createElement('input');
            deleteBtn.type = "button";
            deleteBtn.className = "button";
            deleteBtn.value = "Delete";
            deleteBtn.style = "margin-right:16px"
            deleteBtn.onclick = function () {
            alert("Delete: " + user._uid);
            };
            action.appendChild(deleteBtn);  

            // add data to row
            tr.appendChild(name);
            tr.appendChild(id);
            tr.appendChild(action);

            // add row to table
            table.appendChild(tr);
        });
        
</script>