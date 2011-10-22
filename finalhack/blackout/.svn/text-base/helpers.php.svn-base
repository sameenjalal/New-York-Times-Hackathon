<?php
	/** This is a nice version of print_r you can use while debugging webpages. It'll print the array prettier. */
	function debug_r($arr)
	{
		echo '<pre>';
		print_r($arr);
		echo '</pre>';
	}

	/** This function prints out the html encoded version of text. If you are printing out a variable and you know it doesn't contain html, use encho() instead of echo(). Helps a lot in avoiding XSS bugs. */
	function encho($text)
	{
		echo htmlspecialchars($text);
	}

	define('DB_USER', 'samjalal');
	define('DB_PASS', 'akash123');
	define('DB_HOST', 'mysql.sameenjalal.com');
	define('DB_NAME', 'sameen_test');
	
	/** This function connects us to the database defined in the macros above. */
	function db_connect()
	{
		mysql_connect(DB_HOST, DB_USER, DB_PASS);		
		mysql_select_db(DB_NAME);
	}

	/** This function is equivalent to calling mysql_query(sprintf(query, ...)). It will mysql_real_escape all args after the first arg in sprintf.
	 * This is awesome for avoiding SQL injections.
	 * You can set sql_explain=1 in the $_REQUEST to debug sql_queries.
	 */
	function db_query($query)
	{
		$num_args = func_num_args();

		$args = array();

		for($i = 0; $i < $num_args; $i++)
		{
			$args[] = mysql_real_escape_string(func_get_arg($i));
		}

		$query = call_user_func_array('sprintf', $args);

		if($_REQUEST['sql_explain'] == 1)
		{
			debug_r('Query: '.$query."\n";
		}

		mysql_query($query) or die(mysql_error());
	}


	/** This function returns back a list of entries in the table. Each entry is an associative array of stuff.
	 * DO NOT USE THIS FOR BIG TABLES
	 */
	function db_fetch_assoc($res)
	{
		$rv = array();
		while($row = mysql_fetch_assoc($res))
		{
			$rv[] = $row;
		}
		return $rv;
	}
