<meta name="viewport" content="width=device-width, initial-scale=1.0">

<html>
    <h1> Car Catalog </h1>
       <p>Find your ideal car by using the filters provided below</p>
        <header>
        </header>
            <button class="searchbutton" id="search_button">Search</button>
            <div>
                <br>
                <div class="select">
                    <form>
                    <label for="type"> Type:</label>
                        <select name="type" id="type">  
                            <option value="suv">SUV</option>
                            <option value="truck">Truck</option>
                            <option value="minivan">Minivan</option>
                        </select>
                    </form>
                 </div>
                 <br>
                 <div class="select">
                    <form>
                    <label for="powersource"> Powersource:</label>
                        <select name="powersource" id="powersource">  
                            <option value="ice">ICE</option>
                            <option value="hybrid">Hybrid</option>
                            <option value="electric">Electric</option>
                        </select>
                    </form>
                 </div>
                 <br>
                 <div class="select">
                    <form>
                    <label for="PriceRange"> Price Range:</label>
                        <select name="PriceRange" id="PriceRange">  
                            <option value="1">10-20k</option>
                            <option value="2">25-40k</option>
                            <option value="3">40-60k</option>
                        </select>
                    </form>
                </div>
                <br>
                <table class="table-latitude">
                <thead>
                    <tr>
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

    .searchbutton {
        background-color: white;
        border-radius: 8px;
        color: black;
        border: none;
        margin: 0;
        font-family: "Kanit", sans-serif;
        font-size: 16px;
    }

    .searchbutton:hover {
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

</style>


<script>
    const btnSearch = document.getElementById("search_button");
    const resultContainer = document.getElementById("result");
    const type_filter = document.getElementById("type");

    btnSearch.addEventListener('click', (event) => {
          console.log("Search Clicked!");
          var car_type_value = type_filter.value; //sets variable to the value of the filter that the user selects 
          var car_list = getCarResults(car_type_value, "ice", "1"); //setting car_list to the result gotten in the function getCarResults

          console.log("Filtered cars retrieved!");
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

    function getCarResults(type, powersource, pricerange) {
        
        var all_cars = [
            { brand: "toyota", color: "white", type: "van", powersource: "hybrid", price_range: "2"},
            { brand: "honda", color: "red", type: "suv", powersource: "ice", price_range: "1"},
            { brand: "ferrari", color: "black", type: "sports car", powersource: "electric", price_range: "3"},
          ]

        var result = [];
        for (const car of all_cars){
              console.log(car);

            if (car["type"] === type && car["powersource"] === powersource && car["price_range"] === pricerange) {
                result.push(car);
            }
        }

        return result;
    }
  </script>

