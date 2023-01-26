<meta name="viewport" content="width=device-width, initial-scale=1.0">

<html>
    <h1> Car Catalog </h1>
       <p>Find your ideal car by using the filters provided below</p>
        <header>
        </header>
            <div>
                <button class="searchbutton" id="search_button">Search</button>
                <div class="navbar">
                    <form>
                    <label for="Type">Type:</label>
                        <select name="Type" id="type">  
                                <option value="suv">SUV</option>
                                <option value="truck">Truck</option>
                                <option value="minivan">Minivan</option>
                        </select>
                    </form>
                    <form>
                    <label for="engine">Engine:</label>
                        <select name="engine" id="engine">  
                                <option value="ice">ICE</option>
                                <option value="hybrid">Hybrid</option>
                                <option value="electric">Electric</option>
                        </select>
                    </form>
                    <form>
                    <label for="Price Range">Price Range:</label>
                        <select name="Price Range" id="Price Range">  
                                <option value="1">10-20k</option>
                                <option value="2">25-40k</option>
                                <option value="3">40-60k</option>
                        </select>
                    </form>
                </div>
                <table class="table-latitude">
                <thead>
                    <tr>
                        <th>Brand</th>
                        <th>Color</th> 
                        <th>Type</th>
                    </tr>
                    </thead>
                     <tbody id="result">
                    </tbody>
                </table>
            </div>
  </html>

<style>
    .searchbutton {
        background-color: white;
        border-radius: 8px;
        color: black;
        border: none;
        margin: 0;
        font-family: "Kanit", sans-serif;
        font-size: 20px;

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
            { brand: "toyota", color: "white", type: "van", engine: "hybrid", price range: "2"},
            { brand: "honda", color: "red", type: "suv", engine: "ice", price range: "1"},
            { brand: "ferrari", color: "black", type: "sports car", engine: "electric", price range: "3"},
          ]
          var mySearch = document.getElementById("result");
          var rowCount = mySearch.rows.length;
          for (var x=rowCount-1; x>0; x--) {
                mySearch.deleteRow(x);
            }

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

          // this builds ALL td's (cells) into tr element
              tr.appendChild(brand_ele);
              tr.appendChild(color_ele);
              tr.appendChild(type_ele);

              resultContainer.appendChild(tr);
            }
          }
    })

  </script>

