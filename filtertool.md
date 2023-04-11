<meta name="viewport" content="width=device-width, initial-scale=1.0">

<html>
    <h1> Car Filter Tool </h1>
       <p>Find your ideal car by using the filters provided below</p>
          <table id="prices">
            <tr>
                <th>KEY</th>
                <th>Price Range</th>
            </tr>
            <tr>
                <td>1</td>
                <td>10-15k</td>
            </tr>
            <tr>
                <td>2</td>
                <td>20-35k</td>
            </tr>
             <tr>
                <td>3</td>
                <td>40-70k</td>
            </tr>
             <tr>
                <td>4</td>
                <td>80k and up</td>
            </tr>
          </table>
            <br>
            <div>
                <br>
                <div class="select">
                    <form>
                    <label for="brand"> Brand:</label>
                        <select name="brand" id="brand">  
                            <option value=""> </option>
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
                <br>
                <div class="select">
                    <form>
                    <label for="color"> Color:</label>
                        <select name="color" id="color">  
                            <option value=""> </option>
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
                <br>
                <div class="select">
                    <form>
                    <label for="type"> Type:</label>
                        <select name="type" id="type">  
                            <option value=""> </option>
                            <option value="suv">SUV</option>
                            <option value="truck">Truck</option>
                            <option value="sedan">Sedan</option>
                            <option value="sports">Sports</option>
                        </select>
                    </form>
                 </div>
                 <br>
                 <div class="select">
                    <form>
                    <label for="powersource"> Powersource:</label>
                        <select name="powersource" id="powersource">
                            <option value=""> </option>  
                            <option value="ice">ICE</option>
                            <option value="hybrid">Hybrid</option>
                            <option value="electric">Electric</option>
                        </select>
                    </form>
                 </div>
                 <br>
                 <div class="select">
                    <form>
                    <label for="pricerange"> Price Range:</label>
                        <select name="pricerange" id="pricerange">  
                            <option value=""> </option>
                            <option value="1">1</option>
                            <option value="2">2</option>
                            <option value="3">3</option>
                            <option value="4">4</option>
                        </select>
                    </form>
                </div>
                <br>
                <button class="searchbutton" id="search_button">Search</button>
                <br>
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
    const btnSearch = document.getElementById("search_button");
    const resultContainer = document.getElementById("result");
    const brand_filter = document.getElementById("brand");
    const color_filter = document.getElementById("color");
    const type_filter = document.getElementById("type");
    const powersource_filter = document.getElementById("powersource");
    const pricerange_filter = document.getElementById("pricerange");

    let all_cars;
    getAllCars();

    btnSearch.addEventListener('click', (event) => {
          console.log("Search Clicked!");
          clearTable();
          
          var car_brand_value = brand_filter.value;
          var car_color_value = color_filter.value; 
          var car_type_value = type_filter.value; //sets variable to the value of the filter that the user selects
          var car_powersource_value = powersource_filter.value;
          var car_pricerange_value = pricerange_filter.value; 

          var car_list = getCarResults(car_brand_value, car_color_value, car_type_value, car_powersource_value, car_pricerange_value); //setting car_list to the result gotten in the function getCarResults

          if (car_list.length === 0) {
            alert('No Cars Found')
            return
          }

          console.log("Filtered cars retrieved!");
          console.log(car_list);
          console.log("Creating table!");

          for (const car of car_list) {
            console.log(car);

            const tr = document.createElement("tr");
        
            const image_ele = document.createElement("td");
           
            var img = document.createElement('img');
            img.src = "{{ site.baseurl }}/images/" + car.image + ".jpg";
            img.width = "150";
            img.height = "100";
            console.log(img.src);
            image_ele.appendChild(img);

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
            tr.appendChild(image_ele);
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
    
    function getAllCars() {
        fetch('https://finalssvgcars.duckdns.org/api/cars/').then(function(response) {
                return response.json();
            }).then(function(data) {
                console.log(data);
                all_cars = data;
            }).catch(function(err) {
                console.log(err);
            });
    }

    function getCarResults(brand, color, type, powersource, pricerange) {
        var result = [];
        for (const car of all_cars){
              console.log(car);
              console.log("price range from data is:" + typeof car["pricerange"] + car["pricerange"])
              console.log("being compared to:" + typeof pricerange + pricerange)

            if ((car["brand"] === brand || !brand) &&
                (car["color"] === color || !color) &&
                (car["type"] === type || !type) && 
                (car["powersource"] === powersource || !powersource) && 
                (car["pricerange"] === parseInt(pricerange, 10) || !pricerange)) {
                result.push(car);
            }
        }

        return result;
    }
  </script>

