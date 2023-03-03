<meta name="viewport" content="width=device-width, initial-scale=1.0">
<h1> Specs Search </h1>
<p>Search for your dream car using specifications!</p>
<p>Answer these questions with the specifications you want for your dream car! This will help the program narrow down the cars that are a best fit for you!</p>

<html>
    <form onsubmit="validate(); return false;" class="w3-container w3-theme w3-card">
    <h3> 1. What type of car do you wish to buy? </h3>
        <input type="radio" id="type" name="Sedan" value="Sedan">
        <label for="Sedan">Sedan</label><br>
        <input type="radio" id="type" name="SUV" value="SUV">
        <label for="SUV">SUV</label><br>
        <input type="radio" id="type" name="Pickup Truck" value="Pickup Truck">
        <label for="type">Pickup Truck</label><br>
        <input type="radio" id="type" name="Sports Car" value="Sports Car">
        <label for="Sports Car">Sports Car</label><br>
        <input type="radio" id="type" name="Van" value="Van">
        <label for="Van">Van</label><br>
        <input type="radio" id="type" name="Convertible" value="Convertible">
        <label for="Convertible">Convertible</label><br>
        <input type="radio" id="type" name="Coupe" value="Coupe">
        <label for="Coupe">Coupe</label><br>
    <h3> 2. How many people should your car be able to seat?</h3>
        <input type="radio" id="seatingCapacity" name="5" value="5">
        <label for="5">5</label><br>
        <input type="radio" id="seatingCapacity" name="7" value="7">
        <label for="7">7</label><br>
        <input type="radio" id="seatingCapacity" name="8" value="8">
        <label for="8">8</label><br>
        <input type="radio" id="seatingCapacity" name="10" value="10">
        <label for="10">10</label><br>
        <input type="radio" id="seatingCapacity" name="15" value="15">
        <label for="15">15</label><br>
    <h3> 3. What power source do you prefer?</h3>
        <input type="radio" id="powerSource" name="Gasoline" value="Gasoline">
        <label for="Gasoline">Gasoline</label><br>
        <input type="radio" id="powerSource" name="Electric" value="Electric">
        <label for="Electric">Electric</label><br>
    <h3> 4. Transmission Type?</h3>
        <input type="radio" id="transmission" name="Automatic" value="Automatic">
        <label for="Automatic">Automatic</label><br>
        <input type="radio" id="transmission" name="Manual" value="Manual">
        <label for="Manual">Manual</label><br>
    <h3> 5. Desired Mileage (in miles per gallon)</h3>
        <input type="radio" id="mileage" name="Non-Gasoline" value="Non-Gasoline">
        <label for="Non-Gasoline">Non-Gasoline (select if you want an electric car)</label><br>
        <input type="radio" id="mileage" name="a" value="a">
        <label for="a">10-20 MPG</label><br>
        <input type="radio" id="mileage" name="b" value="b">
        <label for="b">21-30 MPG</label><br>
        <input type="radio" id="mileage" name="c" value="c">
        <label for="c">31-40 MPG</label><br>
    <h3> 6. Desired Range (in miles per charge)</h3>
        <input type="radio" id="range" name="Non-Electric" value="Non-Electric">
        <label for="Non-Electric">Non-Electric (select if you want a gasoline car)</label><br>
        <input type="radio" id="range" name="1" value="1">
        <label for="1">200-250 Miles</label><br>
        <input type="radio" id="range" name="2" value="2">
        <label for="2">251-300 Miles</label><br>
        <input type="radio" id="range" name="3" value="3">
        <label for="3">301-350 Miles</label><br>
        <input type="radio" id="range" name="4" value="4">
        <label for="4">351-400 Miles</label><br>
        <input id="submit" type="submit" value="Find Cars" onclick="showTable(); return false;">
    <h3>
</html>

<style>
    .testbutton {
        background-color: white;
        border-radius: 8px;
        color: black;
        border: none;
        margin: 0;
        font-family: "Kanit", sans-serif;
        font-size: 20px;
    }

    .testbutton:hover {
        color: rgb(4, 4, 43);
    }

    label {
        font-family: "Kanit", sans-serif;
        font-size: 18px;
        color: white;
    }

    h3 {
        font-family: "Kanit", sans-serif;
        font-size: 20px;
        color: white;
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
</style>


<script>
            function validate(event) {
                event.preventDefault();
                //Rest of the code
            }
            function search_car() {
                let input = document.getElementById('type').value
                input = input.toLowerCase();
                for (i = 0; i < x.length; i++) {
                    if (!x[i].innerHTML.toLowerCase().includes(input)) {
                        x[i].style.display = "none";
                    }
                    else {
                        x[i].style.display = "list-item";
                    }
                }
            }
            function showTable() {
                alert("fetching");
                const read_options = {
                    method: 'GET', // *GET, POST, PUT, DELETE, etc.
                    mode: 'cors', // no-cors, *cors, same-origin
                    cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
                    credentials: 'omit', // include, *same-origin, omit
                    headers: {
                        'Content-Type': 'application/json'
                    },
                };
                fetch('https://finalssvgcars.duckdns.org/api/carspecs', read_options)
                    .then(response => response.json())
                    .then(data => createTable(data));
                //  $(".table").remove();*/
               //  createTable(data);
               return false;
            }
            function createTable(data)
            {
                alert("Getting data");
                // $("#table").remove();
                var table = "<table class='table' border=1 style='color:#fff !important; background-color:#d09c00 !important'>";
                // add a row for name and marks
                table += `<tr>
                                      <th>Model Name</th>
                                      <th>Type</th>
                                      <th>Seating Capacity</th>
                                      <th>Power Source</th>
                                      <th>Transmission Type</th>
                                      <th>Mileage</th>
                                      <th>Range</th>
                                    </tr>`;
                // now add another row to show subject
                table += `<tr>
                                      <th width=200></th>
                                      <th width=200></th>
                                      <th width=200></th>
                                      <th width=200></th>
                                      <th width=200></th>
                                      <th width=200></th>
                                      <th width=200></th>
                                    </tr>`;
                var tr = "";
                var b = document.getElementById("type").value;
                var c = document.getElementById("seatingCapacity").value;
                var d = document.getElementById("powerSource").value;
                var e = document.getElementById("transmission").value;
                var f = document.getElementById("mileage").value;
                var g = document.getElementById("range").value;
                // alert(data[0].cuisine);
                for (let i = 0; i < data.length; i++) {
                    if (data[i].type.toLowerCase() == b.toLowerCase() && data[i].seatingCapacity.toLowerCase() == c.toLowerCase() && data[i].powerSource.toLowerCase() == d.toLowerCase() && data[i].transmission.toLowerCase() == e.toLowerCase() && data[i].mileage.toLowerCase() == f.toLowerCase() && data[i].range.toLowerCase() == g.toLowerCase()) {
                        //alert(data[i].recipename);
                      tr += "<tr>";
                        tr += `<td>${data[i].name}</td>`;
                        tr += `<td>${data[i].type}</td>`;
                        tr += `<td>${data[i].seatingCapacity}</td>`;
                        tr += `<td>${data[i].powerSource}</td>`;
                        tr += `<td>${data[i].transmission}</td>`;
                        tr += `<td>${data[i].mileage}</td>`;
                        tr += `<td>${data[i].range}</td>`;
                        tr += "</tr>"
                    }
                }
                table += tr + "</table>";
                document.getElementById("table").innerHTML += table;
                document.getElementById("range").value = g;
                document.getElementById("mileage").value = f;
                document.getElementById("transmission").value = e;
                document.getElementById("powerSource").value = d;
                document.getElementById("seatingCapacity").value = c;
                document.getElementById("type").value = b;
                alert("done");
            }
            function HideSuggestRecipe(){
                var x = document.getElementById("submit");
                    x.style.display = "none";
            }
            function UnhideData() {
                var x = document.getElementById("submit");
                x.style.display = "block";
            }
</script>
