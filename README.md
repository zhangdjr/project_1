<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bitcoin Block Hashing Process</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f4;
        }
        h1, h2 {
            color: #333;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            background: white;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #555;
            color: white;
        }
        code {
            display: block;
            background: #eee;
            padding: 10px;
            border-radius: 5px;
            white-space: pre-wrap;
        }
        .image-container {
            text-align: center;
            margin-top: 20px;
        }
        img {
            max-width: 100%;
            border-radius: 8px;
        }
    </style>
</head>
<body>

    <h1>Bitcoin Block Hashing Process</h1>

    <h2>Data Table</h2>
    <table>
        <tr>
            <th>k</th>
            <th>xD</th>
            <th>Hash</th>
            <th>Time (s)</th>
            <th>Trials</th>
        </tr>
        <tr>
            <td>2</td>
            <td>1450081131this_is_a_bitcoin_block_of_62321234</td>
            <td>00a0c454380483174fe3075839163091b90cf90a55c0cdc1cd126db4c73dd06f</td>
            <td>1</td>
            <td>10,000</td>
        </tr>
        <tr>
            <td>3</td>
            <td>1655663793this_is_a_bitcoin_block_of_62321234</td>
            <td>0000dac1581541a743ac79e6e5814438b4d055c0468d257dc2127b5d5bc079ce</td>
            <td>1</td>
            <td>30,000</td>
        </tr>
        <tr>
            <td>4</td>
            <td>719498601this_is_a_bitcoin_block_of_62321234</td>
            <td>0000417ae5759c448e0fed78763ba1f366af88614d88cc756cf2cd6adb9225ac</td>
            <td>1</td>
            <td>50,000</td>
        </tr>
        <tr>
            <td>5</td>
            <td>182792973this_is_a_bitcoin_block_of_62321234</td>
            <td>000009ef410812f54e1d0ebd1445f7a2248caea5ba5eb0d5ea8b4369e3b2dc85</td>
            <td>1</td>
            <td>100,000</td>
        </tr>
        <tr>
            <td>6</td>
            <td>767710983this_is_a_bitcoin_block_of_62321234</td>
            <td>00000005105b1a08b3f748fed406ccbb90304f02a17d18aefc5de9bfebd5106d</td>
            <td>4</td>
            <td>10,000,000</td>
        </tr>
    </table>

    <h2>Explanation of Trials</h2>
    <p>The number of trials was determined through trial and error. If I didn't get the desired hash, I simply increased the number of trials significantly.</p>

    <h2>Code Change</h2>
    <p>I modified the following line:</p>
    <code>
        val nonce = sc.range(0, trials).mapPartitionsWithIndex((indx, iter) => {<br>
            &nbsp;&nbsp;val rand = new scala.util.Random(indx + seed)<br>
            &nbsp;&nbsp;iter.map(x => rand.nextInt(Int.MaxValue - 1) + 1)<br>
        })
    </code>
    <p>to:</p>
    <code>
        val nonce = sc.range(0, trials)
    </code>

    <h2>Screenshot</h2>
    <div class="image-container">
        <img src="https://github.com/user-attachments/assets/f0dd3d94-402d-4f14-9fa6-eb68f93a37ab" alt="Screenshot of the process">
    </div>

</body>
</html>
