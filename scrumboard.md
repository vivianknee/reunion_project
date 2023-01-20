
<style>
    h1 {
        font-family: "Kanit", sans-serif;
        font-size: 30px;
        color: white;
    }

    body {
        font-family: "Kanit", sans-serif;
    }

    table {
        border-collapse: collapse;
        width: 800px;
        height: 200px;
        border: 1px solid white;
    }

    tr {
        transition: all .2s ease-in;
        cursor: pointer;
    }

    tr:hover {
        background-color: white;
        transform: scale(1.02);
        box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.2), -1px -1px 8px rgba(0, 0, 0, 0.2);
    }

    th,
    td {
        padding: 12px;
        text-align: left;
        border-bottom: 1px solid ;
    }

    @media only screen and (max-width: 768px) {
        table {
            width 90%
        }
    }

    .background {
    	background-color: blue;
     }

</style>

<html>
    <h1>Meet the Team!</h1>
    <body>
        <table>
            <tr class="background">
                <th>Group Member</th>
                <th>Scrum Roll</th>
                <th>About</th>
            </tr>
            <tr>
                <td>Shreya Sapkal</td>
                <td>Scrum Master</td>
                <td>
                    <ul>
                        <li>Manage weekly issues</li>
                        <li>Assist in all areas of development</a></li>
                        <li>Manage weekly tasks/sprints</a></li>
                    </ul>
                </td> 
            </tr>
            <tr>
                <td>Sarah Liu</td>
                <td>Backend Developer</td>
                <td>
                    <ul>
                        <li>Manage flask repository</li>
                        <li>Manage code on backend</a></li>
                    </ul>
                </td> 
            </tr>
            <tr>
                <td>Vivian Knee</td>
                <td>Frontend Developer</td>
                <td>
                    <ul>
                        <li>Manage fastpages</li>
                        <li>Manage site</a></li>
                    </ul>
                </td> 
            </tr>
            <tr>
                <td>Giannina</td>
                <td>DevOps Manager</td>
                <td>
                    <ul>
                        <li>Manage aws server</li>
                        <li>Ensure server is updated when a new version is released</a></li>
                    </ul>
                </td> 
            </tr>
        <table>
    </body>
</html>