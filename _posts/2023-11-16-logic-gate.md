<html>
<head>
    <style>
       .rectangle1 {
        position:absolute;
        background-color:#b5ceff;
        height: 100%;
        width: 100%;
        }
        #header {
            background-color: #ffffff;
            padding: 10px;
            text-align: center;
            font-family: JetBrainsMono; 
        }
        #button-container {
            text-align: center;
            position: absolute;
            top: 170px; /* Adjust the top position as needed */
            left: 50%;
            transform: translateX(-50%);
        }
        .page-button {
            display: inline-block;
            margin: 0 10px;
            padding: 10px 20px;
            font-size: 16px;
            text-decoration: none;
            background-color: #246FFF;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="button-container">
        <a class="page-button" href="page1.html">AND</a>
        <a class="page-button" href="page2.html">OR</a>
        <a class="page-button" href="page3.html">XOR 3</a>
        <a class="page-button" href="page4.html">NAND</a>
        <a class="page-button" href="page5.html">NOR</a>
        <a class="page-button" href="page6.html">XNOR</a>
    </div>
</body>
</html>
