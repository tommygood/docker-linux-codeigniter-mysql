# docker-linux-codeigniter-mysql
## Intro

Building the <b>Codeigniter 3</b> + <b>PHP 8</b> on docker with docker-compose

## Prerequisite

- docker
- docker-compose

## Installation

1. `git clone https://github.com/tommygood/docker-linux-codeigniter-mysql.git`

## Configuration

- Replace the `ciapp` to your CI project (<b>Not Neccessary</b>)
   
   - `mv ciapp {others_name}`
   - `mv /{path_to_your_ci} ./ciapp`
   
   - `ciapp/.htaccess`
     
	   ```
	   RewriteEngine on
	   RewriteCond $1 !^(index\.php|images|robots\.txt)
	   <IfModule mod_rewrite.c>
	   RewriteEngine On
	   RewriteBase /
	   RewriteCond %{REQUEST_FILENAME} !-d
	   RewriteCond %{REQUEST_FILENAME} !-f
	   RewriteRule ^(.*)$ index.php?url=$1 [QSA,L]
	   </IfModule>
	   ```
    
    - `ciapp/application/config/database.php`
	
		```
		$db['default'] = array(
		'dsn'	=> '',
		'hostname' => 'db',
		'username' => 'admin',
		'password' => 'admin',
		'database' => 'ciapp',
		```

## Usage

1. `docker-compose up -d --build`
2. open browser on http://localhost:8000/

## Reference
- https://github.com/abhishek70/docker-linux-codeigniter-mysql
