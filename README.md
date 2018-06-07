# Web-Storage-Sample
This is a basic sample code for understanding HTML5 Basic Storage API - Session &amp; Local Storage

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Web Storage</title>
    <script>
    function saveData_session(){
        var name = document.getElementById('name');
        var value = document.getElementById('value');
        sessionStorage.setItem(name.value, value.value);
        display();
    }
    function saveData_local(){
        var name = document.getElementById('name');
        var value = document.getElementById('value');
        localStorage.setItem(name.value, value.value);
        display();
    }
    function display(){
        var display = document.getElementById('output_data');
        display.innerHTML = "Session Storage : <br>";
        for (var property in sessionStorage) {
            if (sessionStorage.hasOwnProperty(property)) {
                display.innerHTML += property + " : " + sessionStorage.getItem(property) + "</br>";
            }
        }

        display.innerHTML += "<br>Local Storage : <br>";
        for (var property in localStorage) {
            if (localStorage.hasOwnProperty(property)) {
                display.innerHTML += property + " : " + localStorage.getItem(property) + "</br>";
            }
        }
        
    }
    </script>
</head>
<body onload="display()">
    <form action="">
        Enter Key Name : <input type="text" id="name"><br>
        Enter Key Value : <input type="text" id="value"><br>
        <input type="button" value="Save In Session Storage" onclick="saveData_session()">
        <input type="button" value="Save In Local Storage" onclick="saveData_local()">
    </form><br>
    <div id="output_data"></div>
</body>
</html>
