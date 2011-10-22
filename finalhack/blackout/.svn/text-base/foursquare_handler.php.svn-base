<?

	include('helpers.php');

	$url = 'https://foursquare.com/oauth2/access_token?client_id=BBGNM1UQHHNWJWXDALCVLG5C1JLQMLLMQPIR1UYA0AU3ERNK&client_secret=WHRZV0W2ZFJPY2CMSEXB5H1VNKFLFWY53ZLLH0ZQLTDIRTNG&grant_type=authorization_code&redirect_uri=http://sameenjalal.com/blackout/foursquare_handler.php&code='.$_REQUEST['code'];

	$temp= file_get_contents($url);

	$temp = json_decode($temp);

	debug_r($temp);

	$url2 = 'https://api.foursquare.com/v2/users/self?oauth_token='.$temp->access_token;

	$temp2 = file_get_contents($url2);




	$output = json_decode($temp2);

	debug_r($output);
	
	
?>
