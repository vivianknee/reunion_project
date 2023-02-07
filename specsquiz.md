<meta name="viewport" content="width=device-width, initial-scale=1.0">
<h1> Specs Search </h1>
<p>Answer these questions with the specifications you want for your dream car!</p>


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
        <label for="a">a</label><br>
        <input type="radio" id="html" name="mileage" value="b">
        <label for="b">b</label><br>
        <input type="radio" id="html" name="mileage" value="c">
        <label for="c">c</label><br>
    <h3> 6. Desired Range (in miles per charge)</h3>
        <input type="radio" id="html" name="mileage" value="Non-Electric">
        <label for="Non-Electric">Non-Electric (select if you want a gasoline car)</label><br>
        <input type="radio" id="html" name="mileage" value="1">
        <label for="1">1</label><br>
        <input type="radio" id="html" name="mileage" value="2">
        <label for="2">2</label><br>
        <input type="radio" id="html" name="mileage" value="3">
        <label for="3">3</label><br>
        <input type="radio" id="html" name="mileage" value="4">
        <label for="4">4</label><br>
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

*result goes here*

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
