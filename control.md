<!doctype html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<meta https-equiv="X-UA-Compatible" content="IE=edge,chrome=1">

	<title>IoT Pet Feeder</title>
	<meta name="description" content="Iot Pet Feeder">
	<meta name="author" content="Anchal Bhalla">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<style>
	* { -moz-box-sizing: border-box; -webkit-box-sizing: border-box; box-sizing: border-box; }
	body {
		font-family: "HelveticaNeue-Light", "Helvetica Neue Light", "Helvetica Neue", "Roboto Light", "Segoe UI Web Light", "Segoe UI Light", "Segoe UI Web Regular", "Segoe UI", Helvetica, Arial, sans-serif; 
		margin: 1em;
	}
	header {
		margin-bottom: 2em;
	}
	h1, h2, h3 {
		margin: 0;
		text-rendering: optimizeLegibility;
	}
	h1 {
		font-size: 2.4em;
		line-height: 1.4em;
		text-transform: lowercase;
		font-weight: normal;
		text-shadow: 1px 2px 0 #fff;
	}
	h2 {
		font-size: 1em;
		text-transform: uppercase;
		font-weight: normal;
		text-shadow: 1px 1px 0 #fff;
	}
	footer {
		position: absolute;
		bottom: 2em;
	}
	#main {
		margin: 4em auto;
		text-align: center;
		position: relative;
	}  


	
	</style>
</head>

<body>
	<header>
		<h1> Turning lights on and off</h1>
		<h2>Thank you technology</h2>
	</header>

	<section id="main" role="main">
		<img src="bulb.png" width="400">
		<button id = "lighton" style="height:70px;width:100px; background-color: #4CAF50;">ON</button> 
		<button id = "lightoff" style="height:70px;width:100px; background-color: red;">OFF </button>

	</section> 

	

	<footer>
		The Assembly
	</footer>

	<!-- including the latest PubNub JavaScript SDK -->
	<script src="https://cdn.pubnub.com/pubnub-3.7.10.js"></script>
	<script>
(function() {
   // DOM
   var button1 = document.getElementById("lighton");
   // This is the channel name you are subscribing in Main.py
   var channel = 'auto_control';
   // Init - Get your own keys at admin.pubnub.com
   var p = PUBNUB.init({
      subscribe_key: 'sub-c-f59674be-a2c8-11e7-90db-92dc6f0eccb3',
      publish_key:   'pub-c-9aa1dba9-30d0-4e1b-9a20-dd440f54c3d7' ,
      ssl:true
   });
   // Sending data
   function senddata() {
      
    p.publish({
      channel : channel, 
      message : 'a'
    });
  }
    // Click event
   button1.addEventListener('click', senddata);
})();
	</script> 


	<script>
(function() {
   // DOM
   var button1 = document.getElementById("lightoff");
   // This is the channel name you are subscribing in Main.py
   var channel = 'auto_control';
   // Init - Get your own keys at admin.pubnub.com
   var p = PUBNUB.init({
      subscribe_key: 'sub-c-f59674be-a2c8-11e7-90db-92dc6f0eccb3',
      publish_key:   'pub-c-9aa1dba9-30d0-4e1b-9a20-dd440f54c3d7' ,
      ssl:true
   });
   // Sending data
   function senddata() {
      
    p.publish({
      channel : channel, 
      message : 'b'
    });
  }
    // Click event
   button1.addEventListener('click', senddata);
})();
	</script>
	
</body>
</html>
