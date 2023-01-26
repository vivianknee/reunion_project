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
                    <label for="cars">Type:</label>
                        <select name="Type" id="type">  
                                <option value="suv">SUV</option>
                                <option value="truck">Truck</option>
                                <option value="minivan">Minivan</option>
                        </select>
                    </form>
                </div>
                <table class="table-latitude">
                <thead>
                    <tr>
                        <th>Brand</th>
                        <th>Color</th>
                        <th>New?</th>
                        <th>Year</th>
                        <th>Type</th>
                    </tr>
                    </thead>
                     <tbody id="result">
                    </tbody>
                </table>
            </div>
  </html>

<style>
    body {
        font-family: "Kanit", sans-serif;
        }

    .navbar {
        overflow: hidden;
    }

    .navbar a {
        float: left;
        font-size: 16px;
        color: white;
        text-align: center;
        padding: 14px 16px;
        text-decoration: none;
    }

    .dropdown {
        float: left;
        overflow: hidden;
    }

    .dropdown .dropbtn {
        font-size: 16px;  
        border: none;
        outline: none;
        color: white;
        padding: 14px 16px;
        background-color: inherit;
        font-family: inherit;
        margin: 0;
    }

    .navbar a:hover, .dropdown:hover .dropbtn {
        background-color: navy;
    }

    .dropdown-content {
        display: none;
        position: absolute;
        background-color: #f9f9f9;
        min-width: 160px;
        box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
        z-index: 1;
    }

    .dropdown-content a {
        float: none;
        color: black;
        padding: 12px 16px;
        text-decoration: none;
        display: block;
        text-align: left;
    }

    .dropdown-content a:hover {
        background-color: white;
    }

    .dropdown:hover .dropdown-content {
        display: block;
    }

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

    btnSearch.addEventListener('click', (event) => {
          var car_list = [
            { brand: "toyota", color: "white", is_new: "True", year: 2000, type: "van"},
            { brand: "honda", color: "red", is_new: "False", year: 1995, type: "suv"},
            { brand: "ferrari", color: "black", is_new: "True", year: 2015, type: "sports car"},
          ]

          for (const car of car_list){
              console.log(car);
          
              const tr = document.createElement("tr");
          
              const brand_ele = document.createElement("td");
              brand_ele.innerHTML = car.brand;

              const color_ele = document.createElement("td");
              color_ele.innerHTML = car.color;

              const isnew_ele = document.createElement("td");
              isnew_ele.innerHTML = car.isnew;

              const year_ele = document.createElement("td");
              year_ele.innerHTML = car.year.toString();

              const type_ele = document.createElement("td");
              type_ele.innerHTML = car.type;

          // this builds ALL td's (cells) into tr element
              tr.appendChild(brand_ele);
              tr.appendChild(color_ele);
              tr.appendChild(isnew_ele);
              tr.appendChild(year_ele);
              tr.appendChild(type_ele);

              resultContainer.appendChild(tr);
          }
    })

  </script>

