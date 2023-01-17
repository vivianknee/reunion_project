<!-- Slideshow container -->
<html>
        <header>
            <div class="">
                <button id="search_button">Search</button>
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
        </header>
  </html>

<script>
    const btnSearch = document.getElementById("search_button");
    const resultContainer = document.getElementById("result");

    btnSearch.addEventListener('click', (event) => {
          alert("Hi");
          var car_list = [
            { brand: "toyota", color: "white", is_new: True, year: 2000, type: "van"},
            { brand: "honda", color: "red", is_new: False, year: 1995, type: "suv"},
            { brand: "ferrari", color: "black", is_new: True, year: 2015, type: "sports car"},
          ]

          for (const car of car_list){
              console.log(car);
          
              const tr = document.createElement("tr");
          
              const brand_ele = document.createElement("td");
              brand_ele.innerHTML = car.brand;

              const color_ele = document.createElement("td");
              color_ele.innerHTML = car.color;

              const isnew_ele = document.createElement("td");
              isnew_ele.innerHTML = car.isnew.toString();

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

              tr.appendChild(status);
              resultContainer.appendChild(tr);
          }
    })

  </script>
























<div class="slideshow-container">

  <!-- Full-width images with number and caption text -->
  <div class="mySlides fade">
    <div class="numbertext">1 / 3</div>
    <img src="/images/carslide1.jpg" style="width:100%">
    <div class="text">Caption Text</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">2 / 3</div>
    <img src="/images/carslide2.jpg" style="width:100%">
    <div class="text">Caption Two</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">3 / 3</div>
    <img src="/images/carslide3.jpg" style="width:100%">
    <div class="text">Caption Three</div>
  </div>

  <!-- Next and previous buttons -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>
<br>

<!-- The dots/circles -->
<div style="text-align:center">
  <span class="dot" onclick="currentSlide(1)"></span>
  <span class="dot" onclick="currentSlide(2)"></span>
  <span class="dot" onclick="currentSlide(3)"></span>
</div>

