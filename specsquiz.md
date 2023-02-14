<meta name="viewport" content="width=device-width, initial-scale=1.0">
<h1> Specs Search </h1>

<p>Answer these questions with the specifications you want for your dream car!</p>
<p>These are some of the questions that users will be prompted to answer. They will help the program narrow down the cars that are a best fit for them</p>


<html>
    <h3> 1. What type of car do you wish to buy? </h3>
        <input type="radio" id="html" name="carType" value="Sedan">
        <label for="Sedan">Sedan</label><br>
        <input type="radio" id="html" name="carType" value="SUV">
        <label for="SUV">SUV</label><br>
        <input type="radio" id="html" name="carType" value="Pickup Truck">
        <label for="Pickup Truck">Pickup Truck</label><br>
        <input type="radio" id="html" name="carType" value="Sports Car">
        <label for="Sports Car">Sports Car</label><br>
        <input type="radio" id="html" name="carType" value="Van">
        <label for="Van">Van</label><br>
        <input type="radio" id="html" name="carType" value="Convertible">
        <label for="Convertible">Convertible</label><br>
        <input type="radio" id="html" name="carType" value="Coupe">
        <label for="Coupe">Coupe</label><br>
    <h3> 2. How many people should your car be able to seat?</h3>
        <input type="radio" id="html" name="seatNumber" value="2">
        <label for="2">2</label><br>
        <input type="radio" id="html" name="seatNumber" value="5">
        <label for="5">5</label><br>
        <input type="radio" id="html" name="seatNumber" value="7">
        <label for="7">7</label><br>
        <input type="radio" id="html" name="seatNumber" value="8">
        <label for="8">8</label><br>
        <input type="radio" id="html" name="seatNumber" value="10">
        <label for="10">10</label><br>
        <input type="radio" id="html" name="seatNumber" value="15">
        <label for="15">15</label><br>
    <h3> 3. What power source do you prefer?</h3>
        <input type="radio" id="html" name="powerSource" value="Gasoline">
        <label for="Gasoline">Gasoline</label><br>
        <input type="radio" id="html" name="powerSource" value="Electric">
        <label for="Electric">Electric</label><br>
    <h3> 4. Transmission Type?</h3>
        <input type="radio" id="html" name="transmission" value="Automatic">
        <label for="Automatic">Automatic</label><br>
        <input type="radio" id="html" name="transmission" value="Manual">
        <label for="Manual">Manual</label><br>
    <h3> 5. Desired Mileage (in miles per gallon)</h3>
        <input type="radio" id="html" name="mileage" value="Non-Gasoline">
        <label for="Non-Gasoline">Non-Gasoline (select if you want an electric car)</label><br>
        <input type="radio" id="html" name="mileage" value="a">
        <label for="a">10-20 MPG</label><br>
        <input type="radio" id="html" name="mileage" value="b">
        <label for="b">21-30 MPG</label><br>
        <input type="radio" id="html" name="mileage" value="c">
        <label for="c">31-40 MPG</label><br>
    <h3> 6. Desired Range (in miles per charge)</h3>
        <input type="radio" id="html" name="mileage" value="Non-Electric">
        <label for="Non-Electric">Non-Electric (select if you want a gasoline car)</label><br>
        <input type="radio" id="html" name="mileage" value="1">
        <label for="1">200-250 Miles</label><br>
        <input type="radio" id="html" name="mileage" value="2">
        <label for="2">251-300 Miles</label><br>
        <input type="radio" id="html" name="mileage" value="3">
        <label for="3">301-350 Miles</label><br>
        <input type="radio" id="html" name="mileage" value="4">
        <label for="4">351-400 Miles</label><br>
    <button class="testbutton">Submit</button>
    <table class="table-latitude">
                <thead>
                    <tr>
                        <th>Type</th>
                        <th>Seating Capacity</th> 
                        <th>Power Source</th>
                        <th>Transmission Type</th>
                        <th>Mileage</th>
                        <th>Range</th>
                    </tr>
                    </thead>
                     <tbody id="result">
                    </tbody>
                </table>
</html>

<script>
    const btnSearch = document.getElementById("search_button");
    const resultContainer = document.getElementById("result");
    const type_answer = document.getElementById("type"); // modify all stuff below
    const color_filter = document.getElementById("color");
    const type_filter = document.getElementById("type");
    const powersource_filter = document.getElementById("powersource");
    const pricerange_filter = document.getElementById("pricerange");

    let all_carspecs;
    getAllCarSpecs();

    btnSearch.addEventListener('click', (event) => {
          console.log("Search Clicked!");
          clearTable();
          
          var car_brand_value = brand_filter.value;
          var car_color_value = color_filter.value; 
          var car_type_value = type_filter.value; //sets variable to the value of the filter that the user selects
          var car_powersource_value = powersource_filter.value;
          var car_pricerange_value = pricerange_filter.value; 

          var car_list = getCarSpecs(car_brand_value, car_color_value, car_type_value, car_powersource_value, car_pricerange_value); //setting car_list to the result gotten in the function getCarResults

          if (car_list.length === 0) {
            alert('No Cars Found')
            return
          }

          console.log("Filtered car specs retrieved!");
          console.log(car_list);
          console.log("Creating table!");

          for (const car of car_list) {
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
            price_ele.innerHTML = car.price_range;

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

    function getAllCarSpecs() {
        fetch('http://127.0.0.1:8086/api/cars/').then(function(response) { // make a new api and a new path in backend carspec.api
                return response.json();
            }).then(function(data) {
                console.log(data);
                all_carspecs = data;
            }).catch(function(err) {
                console.log(err);
            });
    }

    function getCarSpecs(brand, color, type, powersource, pricerange) {
        var result = [];
        for (const car of all_carspecs){
              console.log(car);

            if ((car["brand"] === brand || !brand) &&
                (car["color"] === color || !color) &&
                (car["type"] === type || !type) && 
                (car["powersource"] === powersource || !powersource) && 
                (car["price_range"] === pricerange || !pricerange)) {
                result.push(car);
            }

        }

        return result;
    }
</script>

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
