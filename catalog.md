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
                    <label for="engine"> Engine:</label>
                        <select name="engine" id="engine">  
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
                        <th>Engine</th>
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
          var car_list = [
            { brand: "toyota", color: "white", type: "van", engine: "hybrid", price_range: "2"},
            { brand: "honda", color: "red", type: "suv", engine: "ice", price_range: "1"},
            { brand: "ferrari", color: "black", type: "sports car", engine: "electric", price_range: "3"},
          ]
          
          var value = type_filter.value; 

          for (const car of car_list){
              console.log(car);

            if (car["type"] === value)
                {
                const tr = document.createElement("tr");
            
                const brand_ele = document.createElement("td");
                brand_ele.innerHTML = car.brand;

                const color_ele = document.createElement("td");
                color_ele.innerHTML = car.color;

                const type_ele = document.createElement("td");
                type_ele.innerHTML = car.type;

                const engine = document.createElement("td");
                engine.innerHTML = car.engine;

                const price = document.createElement("td");
                price.innerHTML = car.price;

            // this builds ALL td's (cells) into tr element
                tr.appendChild(brand_ele);
                tr.appendChild(color_ele);
                tr.appendChild(type_ele);
                tr.appendChild(engine);
                tr.appendChild(price);

                resultContainer.appendChild(tr);
                }
          }
    })

  </script>

