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
        <p>Take a look at what you like!</p> 