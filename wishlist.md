<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    > div {
        backdrop-filter: blur(30px);
        display: flex;
        width: 100%;
        height: 300px;
        justify-content: center;
        align-items: center;
        a {
            display: block;
            width: 250px;
            height: 130px;
            text-decoration: none;
            img {
                display: block;
                margin: 0 auto 10px auto;
                width: 100px;
                height: 100px;
                border-radius: 50px;
                transition: all 250ms ease-in-out 0s;
            }
            h1 {
                display: block;
                height: 20px;
                line-height: 20px;
                color: white;
                font-weight: bold;
                font-size: 18px;
                text-align: center;
            }
            p {
                display: block;
                font-size: 12px;
                text-align: center;
                color: lightgray;
            }
            &:hover {
                img {
                    transform: scale(1.05);
                }
            }
        }
    }
    button {
        position: absolute;
        cursor: pointer;
        bottom: -20px;
        left: 0;
        right: 0;
        margin: 0 auto;
        background: #10c694;
        height: 40px;
        color: white;
        border: none;
        font-size: 12px;
        padding: 0 60px;
        border-radius: 20px;
        text-transform: uppercase;
        transition: all 250ms ease-in-out 0s;
        &:hover {
            background: ${Color('#10c694').darken(0.2).toString()};
        }
    }
`;
</style>

<html>
    <h1> Wishlist </h1>
        <p>Your personal wishlist</p> 
    <body>
        <p><a href="http://localhost:4001/filtertool">Click here to find more cars</a></p>
        <table>
            <tr>
                <th>Image</th>
                <th>Brand</th>
                <th>Type</th>
                <th>Color</th>
                <th>Powersource</th>
                <th>Price Range</th>
            </tr>
        </table>
    </body>
</html>

<script>
     function getAllCars() {
        fetch('http://127.0.0.1:8080/api/cars/').then(function(response) {
                return response.json();
            }).then(function(data) {
                console.log(data);
                all_cars = data;
            }).catch(function(err) {
                console.log(err);
            });
    }
    var car_list = getAllCars(_image, _brand, _type, _color, _powersource, _pricerange);
    
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
   </script> 
    