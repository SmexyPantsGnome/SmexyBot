SmexyBot
========

Irc Bot designed for Twitch or Hitbox coded in PHP

Requirement to run this bot:
  Web server 
  Database server
  PHP server
  
I used LAMP for linux while designing the PHP code, find instructions for setting this with google search "How To Install Linux, Apache, MySQL, PHP (LAMP)"

Similar software for Windows and Mac.
WAMP (Windows)
MAMP (Macintosh)

To make the bot work extract files to your www/ folder.
Choose either hitbox or twitch folder, modify settings in config.php
Example of Config.php:
  <?php
    //irc settings
    $ircserver = "irc.glados.tv";
    $ircport = 6667;
    $ircnick = "mynick"; 		      //hitbox username
    $ircpass = "mypass"; 		      //hitbox password
    $ircchannel = "#mychannel"; 	//channel you want to join with # symbol in front of it
    //database settings
    $dbhost="localhost";	 	      //ip address of database to connect to
    $dbuser="root"; 		          //database username
    $dbpass="mypass";		          //database password
    $dbname="chat_bot"; 		      //database name to connect to, if it doesn't exist run setup_db.php to create it
  ?>
  
Open http://localhost/hitbox/setup_db.php
  This creates the database that enables the songrequest feature to work.
    
To connect bot to the chat server open http://localhost/hitbox/irc_bot.php
  This will constant run, webbrowser should show the loading symbol while running.
  If loading bar stops means the bot has crashed or the %quit command was sent.
  
To listen to requested songs open http://localhost/hitbox/Youtube_playlist.php

Commands this irc bot has coded:
  %sayit        - responds with 1 of 9 random sayings
  %song text    - adds the youtube tag "text" to the database playlist
  %twitter text - responds with Follow at twitter at http://twitter.com/"text"
  %duration     - responds with how long the current song is in seconds
  %quit         - bot leaves the channel and disconnects from the irc server
