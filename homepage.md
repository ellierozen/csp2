<html>
<head>
    <style>
        body {
            background-color: #006FB9;
        }
        .rectangle2 {
            background-color: #FFF;
            height: 56px;
            width: 190;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-radius: 10px;
        }
        .button {
            color: #000000;
            font-size: 20px;
            font-family: sans-serif;
            line-height: auto;
            border-style: hidden;
            outline: none;
            background: none;
            border: none;
            cursor: pointer;
            text-align: center;
        }
        .button:hover {
            text-decoration: underline;
        }
        .arthub {
            font-size: 36px;
            width: auto;
        }
        .dropdown {
            position: relative;
            display: inline-block;
        }
        .dropdown-content {
            display: none;
            position: absolute;
            background-color: #f9f9f9;
            min-width: 160px;
            box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
            z-index: 1;
        }
        h1 {
            font-size: 40px;
            color: #111;
            text-align: center;
            margin-top: 20px;
        }
        .card {
          box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
          transition: 0.3s;
          width: 50%;
          background-color: #90E9EF;
          margin: 0 auto; /* Center the card */
        }

        .card:hover {
          box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
        }

        .container {
          padding: 2px 16px;
        }
    </style>
</head>
<body>
    <img src="images/water.png" alt="image 1" width="800" height="100">
        <!-- Dropdown -->
       <div id='rectangle2' class='rectangle2'>
        <div class="dropdown">
            <button class='button artists' onclick="location.href='//ellierozen.github.io/csp2-/homepage';';">Click here for more!</button>
            <div class="dropdown-content">
                <a href="puthtmlfilehere">Waterpolo Quiz </a>
                <a href="puthtmlfilehere">See Previous Questions </a>
            </div>
        </div>
    	</div>
    <br>
    <center><h1>WaterPolo Guide</h1></center>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- Card 1 -->
    <div class="card">
        <img src="waterpolo-1.png" alt="Avatar" style="width:100%">
        <div class="container">
            <center><h4><b>Use our AI platform to help answer any of 
your pressing questions about WaterPolo</b></h4></center>
            <center><button>Search</button></center>
            <br>
        </div>
    </div>
    <br>
    <br>
    <!-- Card 2 -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <div class="card">
        <img src="waterpolo-2.png" alt="Avatar" style="width:100%">
        <div class="container">
            <center><h4><b>Interested in tracking local games?  Use 
our catalog below to enter any teams you’re interested in watching!</b></h4></center>
            <center><button>Search</button></center>
            <br>
        </div>
    </div>
    <br>
    <br>
</body>
</html>
