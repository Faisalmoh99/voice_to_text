<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>My Page</title>
</head>
<body>
	<form action="mypage.php" method="get">
		<label for="myvariable">Enter a value:</label>
		<input type="text" id="myvariable" name="myvariable">
		<input type="submit" value="Submit">
	</form>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>My SQL Database Page</title>
</head>
<body>
  <h1>My SQL Database</h1>
  <p>This page connects to a SQL database and displays the results of a query.</p>
  <script>
    // Connect to the database
    var conn = mysql.connector.connect(
      host="127.0.0.1",
      user="",
      password="",
      database="test"
    );
    // Create a cursor
    var cursor = conn.cursor();
    // Execute a query
    $sql = "SELECT * FROM `data`;";
    // Get the results
    var results = cursor.fetchall();
    // Close the cursor
    cursor.close();
    // Close the connection
    conn.close();
    // Display the results
    for (var i = 0; i < results.length; i++) {
      var row = results[i];
      console.log(row);
    }
  </script>
</body>
</html>

