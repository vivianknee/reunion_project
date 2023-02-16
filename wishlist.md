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
                <th>Car</th>
                <th>Color</th>
                <th>Type</th>
                <th>Powersource</th>
                <th>Price Range</th>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
        </table>
        <button onclick="document.getElementById('id01').style.display='block'">Delete Cars</button>
        <div id="id01" class="modal">
        <span onclick="document.getElementById('id01').style.display='none'" class="close" title="Close Modal">&times;</span>
        <form class="modal-content" action="/action_page.php">
            <div class="container">
            <h1>Delete Cars</h1>
            <p>Are you sure you want to delete these cars?</p>
            <div class="clearfix">
                <button type="button" class="cancelbtn">Cancel</button>
                <button type="button" class="deletebtn">Delete</button>
            </div>
            </div>
        </form>
        </div>
    </body>
</html>

<script>
carDict = {} 

    const resultContainer = document.getElementById("result");

    const btnCar = document.getElementById("btn_get_car");
    
    const url = "";

    const options = {
        method: 'GET', // *GET, POST, PUT, DELETE, etc.
        mode: 'no-cors', // no-cors, *cors, same-origin
        cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
        credentials: 'omit', // include, *same-origin, omit
        headers: {
            'Content-Type': 'application/json'
            // 'Content-Type': 'application/x-www-form-urlencoded',
        },
    };
    // prepare fetch PUT options, clones with JS Spread Operator (...)
    const put_options = {...options, method: 'PUT'}; // clones and replaces method

    btnDiag.addEventListener('click', (event) => {
        carStr = "";
        for (const s in carDict) {
            if (carDict[s]) {
                carStr = carStr + s + ", ";
            }
        }

        fetch(url+"car", options)
            .then(response => {
                if (response.status !== 200) {
                    //error('GET API response failure: ' + response.status);
                    return;
                }
                // valid response will have JSON data
                response.json().then(output => {
                    document.getElementById('output').innerHTML = JSON.stringify(output);
                    console.log(output);
                })
            })
    }) 